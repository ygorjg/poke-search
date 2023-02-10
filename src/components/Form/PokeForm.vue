<template>
  <div>
    <label>Insira o nome do pokémon que deseja buscar:</label>
    <form id="poke-form">
      <input
        type="text"
        id="name"
        name="name"
        v-model="name"
        placeholder="Digite aqui"
      />
      <button type="submit">BUSCAR</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "PokeForm",
};
</script>
