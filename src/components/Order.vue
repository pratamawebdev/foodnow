<script setup>
import { ref } from "vue";

const pizzaMenu = [
  {
    pizzas: [
      {
        id: 1,
        name: "Cheese Pizza",
        price: 8,
        image:
          "https://res.cloudinary.com/dnrorybws/image/upload/v1706788936/Cheese_Pizza_igfqgd.png",
        discount: {
          is_active: false,
          final_price: 8,
        },
        toppings: [
          {
            id: 1,
            name: "Avocado",
            price: 1,
          },
          {
            id: 2,
            name: "Broccoli",
            price: 1,
          },
          {
            id: 3,
            name: "Onions",
            price: 1,
          },
          {
            id: 4,
            name: "Zucchini",
            price: 1,
          },
          {
            id: 8,
            name: "Tuna",
            price: 2,
          },
          {
            id: 11,
            name: "Ham",
            price: 3,
          },
        ],
      },
      {
        id: 2,
        name: "Veggie Pizza",
        price: 10,
        image:
          "https://res.cloudinary.com/dnrorybws/image/upload/v1706788616/Veggie_Pizza_qv9zvg.png",
        discount: {
          is_active: true,
          final_price: 8.5,
          label:
            "https://res.cloudinary.com/dnrorybws/image/upload/v1706788681/ribbon_qtaebe.svg",
        },
        toppings: [
          {
            id: 2,
            name: "Broccoli",
            price: 1,
          },
          {
            id: 3,
            name: "Onions",
            price: 1,
          },
          {
            id: 4,
            name: "Zucchini",
            price: 1,
          },
          {
            id: 5,
            name: "Lobster",
            price: 2,
          },
          {
            id: 6,
            name: "Oyster",
            price: 2,
          },
          {
            id: 7,
            name: "Salmon",
            price: 2,
          },
          {
            id: 9,
            name: "Bacon",
            price: 3,
          },
          {
            id: 11,
            name: "Ham",
            price: 3,
          },
        ],
      },
      {
        id: 3,
        name: "Classical Pizza",
        price: 12,
        image:
          "https://res.cloudinary.com/dnrorybws/image/upload/v1706788616/Classical_Pizza_mawgfl.png",
        discount: {
          is_active: false,
          final_price: 12,
        },
        toppings: [
          {
            id: 2,
            name: "Broccoli",
            price: 1,
          },
          {
            id: 3,
            name: "Onions",
            price: 1,
          },
          {
            id: 4,
            name: "Zucchini",
            price: 1,
          },
          {
            id: 8,
            name: "Tuna",
            price: 2,
          },
          {
            id: 9,
            name: "Bacon",
            price: 3,
          },
          {
            id: 10,
            name: "Duck",
            price: 3,
          },
          {
            id: 11,
            name: "Ham",
            price: 3,
          },
          {
            id: 12,
            name: "Sausage",
            price: 3,
          },
        ],
      },
    ],
    pizzaSizes: [
      {
        id: 1,
        name: "Small",
        extra_price: 0,
      },
      {
        id: 2,
        name: "Medium",
        extra_price: 5,
      },
      {
        id: 3,
        name: "Large",
        extra_price: 7,
      },
    ],
  },
];

const selectedPizza = ref(null);
const selectedToppings = ref([]);

const selectPizza = (pizza) => {
  selectedPizza.value = pizza;

  selectedToppings.value = [];
};

const selectTopping = (topping) => {
  if (selectedToppings.value.includes(topping)) {
    selectedToppings.value = selectedToppings.value.filter(
      (t) => t !== topping
    );
  } else {
    selectedToppings.value = [...selectedToppings.value, topping];
  }
};
</script>

<template>
  <section class="order-container">
    <div class="container">
      <div class="pizza-order">
        <div>
          <h2>Choose your pizza</h2>
          <div class="wrapper">
            <div
              class="pizza-container"
              v-for="pizza in pizzaMenu[0].pizzas"
              :key="pizza.id"
              @click="selectPizza(pizza)"
              :class="{ selected: selectedPizza === pizza }"
            >
              <div class="containers">
                <img :src="pizza.image" alt="" class="" />
                <div class="text-container">
                  <span>{{ pizza.name }}</span>
                  <span>{{ pizza.discount.final_price }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div>
          <h2>Custom Pizza</h2>
          <div class="custom-pizza-wrapper">
            <span class="custom-title">Size</span>
            <ul class="custom-size-wrapper">
              <li><input type="radio" /> <label for="">Small</label></li>
              <li>
                <input type="radio" />
                <label for="">Medium <span>(+5$)</span></label>
              </li>
              <li>
                <input type="radio" />
                <label for="">Large <span>(+7$)</span></label>
              </li>
            </ul>
          </div>
          <div class="custom-pizza-wrapper">
            <span class="custom-title">Toppings</span>
            <div class="custom-topping" v-if="selectedPizza">
              <span
                class="btn"
                v-for="topping in selectedPizza.toppings"
                :key="topping.id"
                >{{ topping.name }}</span
              >
            </div>
          </div>
        </div>
      </div>
      <div class="pizza-payment">
        <div class="payment-container">
          <div v-if="selectedPizza">
            <h3>Payment Summary</h3>
            <ul>
              <li>
                {{ selectedPizza.name
                }}<span>${{ selectedPizza.discount.final_price }}</span>
              </li>
              <li v-for="topping in selectedPizza.toppings" :key="topping.id">
                {{ topping.name }}
                <span>${{ topping.price }}</span>
              </li>
            </ul>
            <hr class="line" />
            <div class="total">
              <h4>Total Price</h4>
              <span>${{}}</span>
            </div>
            <button>Order Now</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.btn {
  background-color: #f8f8f6;
  padding: 10px 40px;
  border-radius: 50px;
  border: 0.1px solid black;
  display: flex;
  align-items: center;
  justify-content: center;
}
.payment-container {
  background-color: #f8f8f6;
  width: 100%;
  max-width: 391px;
  height: fit-content;
  padding: 32px;
  border-radius: 16px;
}

.payment-container h3 {
  color: #e77e23;
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 16px;
}

.payment-container ul li {
  list-style: none;
  padding: 8px;
  color: #626f79;
  font-size: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.payment-container .line {
  height: 1px;
  margin: 24px auto;
}
.payment-container .total {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.payment-container .total h4 {
  font-size: 24px;
  font-weight: 400;
}

.payment-container .total span {
  font-size: 24px;
  font-weight: 700;
  color: #e77e23;
}
.payment-container button {
  padding: 14px 12px;
  border-radius: 50px;
  background-color: #e77e23;
  color: white;
  width: 100%;
  font-size: 18px;
  font-weight: 700;
  border: none;
  margin-top: 24px;
}

.order-container {
  width: 100%;
  margin: 100px auto;
}
.container {
  width: 100%;
  max-width: 80%;
  display: grid;
  grid-template-columns: repeat(1, 2fr 1fr);
  margin-top: 160px;
  margin-left: auto;
  margin-right: auto;
  gap: 20px;
}

.pizza-payment {
  display: flex;
  justify-content: end;
}

.pizza-order {
  display: flex;
  flex-direction: column;
  gap: 160px;
}

h2 {
  font-size: 48px;
  font-weight: 700;
  color: #e77e23;
  margin-bottom: 40px;
}

.wrapper {
  display: flex;
  gap: 30px;
}

.custom-title {
  font-size: 24px;
  font-weight: 700;
}

.custom-size-wrapper {
  list-style: none;
  margin-top: 24px;
  margin-bottom: 24px;
  display: flex;
  gap: 30px;
  font-size: 20px;
}

.custom-size-wrapper span {
  opacity: 0.5;
}

.custom-topping {
  display: grid;
  grid-template-columns: repeat(2, 1fr 1fr);
  gap: 30px;
  margin-top: 35px;
  font-size: 20px;
}

.pizza-container {
  background-color: #e77e23;
  width: 100%;
  max-width: 390px;
  padding: 15.818px;
  border-radius: 16px;
  border: 1px solid rgba(51, 51, 51, 0.1);
  cursor: pointer;
}

.pizza-container .containers {
  display: flex;
  align-items: center;
  justify-content: center;
}

.pizza-container img {
  max-width: 144px;
  width: 100%;
}

.pizza-container .text-container {
  display: flex;
  flex-direction: column;
}
</style>
