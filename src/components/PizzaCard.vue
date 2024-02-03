<script setup>
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
</script>

<template>
  <div
    class="pizza-container"
    v-for="pizza in pizzaMenu[0].pizzas"
    :key="pizza.id"
  >
    <div class="container">
      <img :src="pizza.image" alt="" class="" />
      <div class="text-container">
        <span>{{ pizza.name }}</span>
        <span>{{ pizza.discount.final_price }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.pizza-container {
  background-color: #e77e23;
  width: 100%;
  max-width: 390px;
  padding: 15.818px;
  border-radius: 16px;
  border: 1px solid rgba(51, 51, 51, 0.1);
}

.container {
  display: flex;
  align-items: center;

  justify-content: center;
}

img {
  max-width: 144px;
  width: 100%;
}

.text-container {
  display: flex;
  flex-direction: column;
}
</style>
