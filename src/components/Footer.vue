<template>
  <footer>
    <p>Copyright &copy; 2021</p>
    <router-link to="/">Home</router-link>
    &nbsp;
    <router-link to="/about">About</router-link>
    &nbsp;
    <router-link to="/test">Test</router-link>
  </footer>
</template>

<style scoped>
a {
  color: hsl(50, 0%, 30%);
}
footer {
  margin-top: 30px;
  text-align: center;
}
</style>
