<script>

</script>

<template>

  <header>
    <div class="logo">
      <h1>BOOLFLIX API</h1>
    </div>

    <div class="input-text">
      <input v-model="store.inputValue" type="text">
      <button @click="" type="button">Search</button>
    </div>

  </header>

</template>

<style scoped>
header {
  width: 100%;
  display: flex;
  height: 4rem;
  background-color: black;
  color: red;
  justify-content: space-between;
}

.logo {
  width: 25%;
  height: 100%;
  padding: 1rem;
}

.input-text {
  width: 30%;
  height: 100%;
  align-content: center;
  padding-left: 2rem;
}

input {
  width: 70%;
  padding: 0.1rem;
}

button {
  background-color: red;
  padding: 0.2rem;
}
</style>
