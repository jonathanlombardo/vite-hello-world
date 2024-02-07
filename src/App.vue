<script>
import MyTitle from "./components/MyTitle.vue";
import Jumbo from "./components/Jumbo.vue";
export default {
  data() {
    return {
      changingText: {
        textShowed: "",
        texts: ["Project", "Website", "Page", "Layout"],
        i: 1,
      },
    };
  },

  methods: {
    changeText() {
      this.changingText.textShowed = this.changingText.texts[0];

      setInterval(() => {
        this.changingText.textShowed = this.changingText.texts[this.changingText.i];

        if (this.changingText.i < this.changingText.texts.length - 1) {
          this.changingText.i++;
        } else {
          this.changingText.i = 0;
        }
      }, 1000);
    },
  },

  created() {
    this.changeText();
  },

  components: { MyTitle, Jumbo },
};
</script>

<template>
  <header>
    <MyTitle :msg="'This is my first Vite ' + changingText.textShowed" />
  </header>
  <main>
    <Jumbo />
  </main>
</template>

<style>
@import url(./style.css);
@import url(../node_modules/bootstrap/dist/css/bootstrap.css);

header,
main,
#app {
  display: flex;
  justify-content: center;
  align-items: center;
}

#app {
  flex-direction: column;
  gap: 20px;
  background-image: linear-gradient(to right, #49c7ff, #bd34fe);
  height: 100vh;
}
</style>
