<template>
  <q-page class="container flex column justify-around flex-center">
    <q-img
      src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_UQh51rKjZ66Ii_7lJKyI7ZRDspXIdrbPfA&usqp=CAU"
      spinner-color="red"
      style="height: 220px; max-width: 230px"
    />
    <h4 class="title q-ma-sm text-center">{{ phrases[index] }}</h4>
    <q-btn class="button" rounded  label="Gerar Frase"  @click="randomPosition" />
  </q-page>
</template>

<script>
export default {
  name: "Frase do dia",
  data() {
    return {
      phrases: [
        "Os carros são minha terapia sobre rodas.",
        "O carro é a maior invenção do homem.",
        "Quatro rodas, um motor, uma paixão que me faz sentir vivo.",
        "Eu não coleciono carros, eu coleciono histórias de aventura.",
      ],
      index: 0,
    };
  },

  methods: {
    randomPosition() {
      let index = parseInt(Math.random() * 4 + 0);
      console.log(index);
      this.index = index;
    },
  },

  beforeMount() {
    this.randomPosition();
  },
};
</script>

<style lang="stylus" scoped>
.container {
  background-color: 	#87CEEB;
}

.title {
  color: #fff;
}

.button {
  background-color: #262525;
  color: #fff;
  width: 90%;
  height: 50px;
}
</style>
