<template lang="html">
  <header class="header">
    <img src="../../assets/logo.png">
    <h1>D . O . T . S</h1>
    <div id="nav">
      <router-link to="/">HOME</router-link> |
      <router-link to="/about">ABOUT</router-link>
    </div>
  </header>
</template>


<style lang="css" scoped>
.header {
  text-align: center;
  width: 100%;
  padding: 1em;
}

.header a {
  color: var(--white);
  padding: 0 .5em;
  text-decoration: none;
}

.header h1 {
  display: inline;
  vertical-align: top;
  font-size: 4.5em;
  padding-left: .5em;
}

.header img {
  height: 70px;
}
</style>
