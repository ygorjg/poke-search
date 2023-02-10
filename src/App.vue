<template>
  <div id="app">
    <HeaderPage />
    <PokeForm />
  </div>
</template>

<script>
import "./styles/global.scss";
import HeaderPage from "./components/HeaderPage/HeaderPage";
import PokeForm from "./components/Form/PokeForm";

export default {
  name: "App",
  components: {
    HeaderPage,
    PokeForm,
  },
};
</script>
