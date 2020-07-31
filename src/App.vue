<template>
  <div id="app">
    <main>
      <Header />
      <router-view/>
    </main>
  </div>
</template>


<script>
import Header from './components/layout/Header';

export default {
  name:"app",
  components: {
    Header
  }
}
</script>


<style>
:root {
  --black: #272727;

  --blue: #90A9B7;
  --blue-dark: #7795A6;

  --lilac: #AC92A6;
  --lilac-dark: #9F7F97;

  --spring: #D2D8B3;
  --spring-dark: #C7CEA1;

  --white: #FCF7ED;
}

::-webkit-scrollbar {
  width: 5px;
  height: 5px;
  left: -100px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

::-webkit-scrollbar-thumb {
  background: var(--blue);
  border-radius: 5px;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  color: var(--black);
  background-color: var(--white);
  overflow: hidden;
}

main {
  margin: auto;
  width: 90vw;
  max-width: 600px;
  margin-top: 1em;

  border-radius: 1em;
  border: 5px solid var(--black);
  background: var(--black);
  color: var(--white);
  box-shadow: .5em .5em 0 rgba(0,0,0, 0.3);
}

button {
  border: none;
  appearance: none;
  outline: none;
  background: var(--blue);
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

button:hover {
  background: var(--blue-dark);
}

button:active {
  -moz-box-shadow: inset 0 0 10px rgba(0,0,0, 0.3);
  -webkit-box-shadow: inset 0 0 10px rgba(0,0,0, 0.3);
  box-shadow: inset 0 0 10px rgba(0,0,0, 0.3);
}

input[type=text] {
  appearance: none;
  outline: none;
  border: none;
}

</style>
