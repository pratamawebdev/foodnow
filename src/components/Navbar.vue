<script setup></script>

<template>
  <nav>
    <div class="container">
      <h1>Food<span>now</span></h1>
      <ul>
        <li><a href="">Home</a></li>
        <li><a href="">Order</a></li>
        <li><a href="">About</a></li>
        <li><a href="">Blog</a></li>
        <li><a href="">Contact us</a></li>
      </ul>
      <div class="container-auth">
        <a href="" class="login-btn">Login</a>
        <a href="" class="register-btn">Register</a>
      </div>
    </div>
  </nav>
</template>

<style scoped>
nav {
  background-color: transparent;
  position: fixed;
  width: 100%;
}
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  max-width: 80%;
  margin: 23px auto;
}
h1 {
  color: #e77e23;
  font-size: 48px;
  font-weight: 700;
}

h1 span {
  color: #f8f8f6;
}
ul {
  display: flex;
  gap: 30px;
  list-style: none;
}
ul li a {
  color: #f8f8f6;
  font-size: 18px;
  font-weight: 700;
  text-decoration: none;
}

.container-auth {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 30px;
}

.container-auth .login-btn {
  background-color: transparent;
  color: #f8f8f6;
  font-weight: 700;
  font-size: 18px;
  padding: 14px 12px;
  border-radius: 50px;
  text-decoration: none;
}

.container-auth .register-btn {
  background-color: #e77e23;
  width: 161px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #f8f8f6;
  padding: 10px 10px;
  font-weight: 700;
  padding: 14px 12px;
  border-radius: 50px;
  text-decoration: none;
}
</style>
