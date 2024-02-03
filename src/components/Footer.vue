<script setup></script>

<template>
  <footer>
    <div class="container">
      <div class="intro">
        <h1>Food<span>now</span></h1>
        <span>Find Us:</span>
        <ul>
          <li><a href="">Icon</a></li>
          <li><a href="">Icon</a></li>
          <li><a href="">Icon</a></li>
        </ul>
      </div>
      <div class="navigation">
        <span>Navigation</span>
        <div class="nav">
          <ul>
            <li>Home</li>
            <li>Order</li>
            <li>About</li>
            <li>Blog</li>
          </ul>
          <ul>
            <li>Home</li>
            <li>Order</li>
            <li>About</li>
            <li>Blog</li>
          </ul>
        </div>
      </div>
      <div class="contact">
        <span class="title">Contact</span>
        <div class="contact-info">
          <span>Food.now@mail.com</span>
          <span>+62848477102943</span>
          <span>+628184938494</span>
        </div>
      </div>
      <div class="location">
        <span class="title">Location</span>
        <div class="location-info">
          <span>Kerobokan </span>
          <p>
            Jl. Raya Kerobokan Br Taman, Kuta No.98, <br />
            Kerobokan Kelod, Kec. Kuta Utara, <br />
            Kabupaten Badung, Bali 80361
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  width: 100%;
  margin: 50px auto;
}

.container {
  width: 100%;
  max-width: 80%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 auto;
}

.intro {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.intro h1 {
  color: #e77e23;
  font-size: 48px;
  font-weight: 700;
}

.intro h1 span {
  color: black;
}

.intro span {
  color: #e77e23;
  font-weight: 700;
}

.intro ul {
  display: flex;
  align-items: center;
  list-style: none;
  text-decoration: none;
  gap: 10px;
}

.intro ul li a {
  text-decoration: none;
  color: #e77e23;
}

.navigation {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.navigation .nav {
  display: flex;
  gap: 50px;
}

.navigation .nav ul li {
  list-style: none;
}

.navigation .nav ul li {
  list-style: none;
  margin-bottom: 10px;
}

.navigation span {
  color: #e77e23;
  font-weight: 700;
}

.contact {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.contact .title {
  color: #e77e23;
  font-weight: 700;
}

.contact .contact-info {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.location {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.location .title {
  font-weight: 700;
  color: #e77e23;
}

.location .location-info {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.location .location-info span {
  font-weight: 700;
}
</style>
