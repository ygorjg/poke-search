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
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
  background: var(--color-background-header);
}

h1 {
  font-family: "Lexend Exa";
  font-style: normal;
  font-weight: 700;
  font-size: 38px;
  line-height: 48px;
  color: var(--color-yellow);
}

span {
  font-size: 25px;
  color: #fff;
}
</style>
