<template>
  <main>
    <form id="poke-form">
      <div class="label-container">
        <h4>Insira o nome do pokémon que deseja buscar:</h4>
      </div>
      <div class="input-container">
        <input
          type="text"
          id="name"
          name="name"
          v-model="name"
          placeholder="Digite aqui"
        />
        <input
          class="btn-submit"
          type="submit"
          value="BUSCAR"
          v-on:click="submitForm"
        />
      </div>
    </form>
    <div class="card-container">
      <div class="card">
        <img :src="pokemon.img" alt="" />
        <p>{{ pokemon.name }}</p>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
export default {
  name: "PokeForm",
  data() {
    return {
      form: {
        name: "",
      },
      pokemon: {
        name: "",
        img: "",
      },
    };
  },
  methods: {
    submitForm(e) {
      e.preventDefault();
      axios
        .get(`https://pokeapi.co/api/v2/pokemon/${this.name}`)
        .then((response) => {
          console.log(response.data);
          this.pokemon.name = response.data.name;
          this.pokemon.img =
            response.data.sprites.other.dream_world.front_default;
        });
    },
  },
};
</script>

<style scoped lang="scss">
main {
  widows: 100vw;
  height: 100vh;
  background-color: #1eb1df;
}
.label-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
}

h4 {
  font-family: "Lexend Exa";
  font-style: normal;
  font-weight: 700;
  font-size: 20px;
  line-height: 25px;
  color: #edff2c;
  text-align: center;
  width: 250px;
  margin-top: 10px;
}
.input-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
}

#name {
  background: #dcdfb7;
  border-radius: 10px 0px 0px 10px;
  border: none;
  width: 180px;
  height: 30px;
}
.btn-submit {
  font-family: "Lexend Exa";
  font-style: normal;
  font-weight: 700;
  font-size: 15px;
  line-height: 19px;
  border: none;
  text-align: center;
  color: #e2f03e;
  background: #5c5e41;
  border-radius: 0px 10px 10px 0px;
  height: 30px;
  width: 80px;
}
.btn-submit:hover {
  cursor: pointer;
  transition: 200ms;
  background-color: #e2f03e;
  color: #5c5e41;
}
.card-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
}

.card {
  background-color:  #5c5e41;
  text-align: center;
}

p {
  font-family: "Lexend Exa";
  font-style: normal;
  font-weight: 700;
  font-size: 20px;
  line-height: 25px;
  color: #edff2c;
  text-align: center;
  width: 250px;
  margin-top: 5px;
}
</style>
