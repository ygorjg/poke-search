<template>
  <header>
    <h1>POKE<span>Search</span></h1>
  </header>
</template>

<script>
export default {
  name: "HeaderPage",
};
</script>

<style scoped lang="scss">
header {
  height: 50px;
  background: var(--color-background-header);
}

h1 {
  color: var(--color-yellow);
}

span {
  color: #fff;
}
</style>
