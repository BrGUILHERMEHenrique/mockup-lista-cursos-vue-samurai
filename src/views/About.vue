<template>
  <div class="about">
    <h1>Sobre:</h1>
    <h3
      style="
        margin: auto;
        padding: 20px;
        display: flex;
        justify-content: justify;
      "
    >
      Esse projeto consiste foi feito durante o curso gratuito de VueJs(Vue
      samurai), algumas alterações foram feitas para estudos, porém o model
      continua parecido! Obrigado por comparecer e ver meu trabalho! meu GitHub
      estará logo abaixo.
    </h3>
    <div
      style="
        display: flex;
        flex: 1;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin-bottom: 5rem;
      "
    >
      <b-button variant="primary" href="https://github.com/BrGUILHERMEHenrique"
        >GitHub</b-button
      >
    </div>
  <div
    style="
      display: flex;
      flex: 1;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    "
  >
    <img :src="github.avatar_url" style="max-width: 15rem; max-height: 15rem" />
    <h3>{{github.name}}</h3>
    <p>{{github.bio}}</p>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      github: {},
    };
  },
  mounted() {
    this.getUser();
  },
  methods: {
    async getUser() {
      try {
        const response = await fetch(
          "https://api.github.com/users/BrGUILHERMEHenrique"
        );
        this.github = await response.json();
        console.log(this.github);
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>
