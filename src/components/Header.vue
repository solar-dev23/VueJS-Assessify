<template>
  <div class="header">
    <h1>Assessify</h1>
    <div class="nav">
      <ul>
        <li><a>About Us</a></li>
        <li><a>Services</a></li>
        <li><a>Play</a></li>
        <li><a>Contact</a></li>
      </ul>
      <div>
        <a>Login</a> /
        <a>Register</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app-header'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  display: flex;
  position: relative;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  height: 88px;
}

h1 {
  margin: 0.5em 1em;
}

.nav {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0.5em 1em;
}

.nav a {
  cursor: pointer;
  color: #42b983;
}

.nav ul li a {
  color: black;
}
</style>
