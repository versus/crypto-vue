<template>
  <div class="wrapper-all">
    <navigationTop />
    <div class="wrapper">
      <div class="wrapper-launchApp">
        <launchApp />
      </div>
      <div class="wrapper-transferContinue">
        <transferContinue />
      </div>
    </div>

    <leadingPlatform />
    <changeSteps />
    <countriesApp />

    <div class="wrapper-FaqAnswers-large">
      <div class="wrapper-FaqAnswers">
        <h1 id="faq">FAQ</h1>
        <p>Найдите ответы, на интересующие вопросы</p>
      </div>
      <div class="wrapper-items-large">
        <div v-for="item in list" :key="item.id">
          <FaqAnswers v-bind:article="item" />
        </div>
      </div>
    </div>

    <changeMoneyFast />
    <footerSocial />
  </div>
</template>

<script>
import navigationTop from "./components/navigationTop.vue";
import launchApp from "./components/launchApp.vue";
import transferContinue from "./components/transfer.vue";
import leadingPlatform from "./components/leadingPlatform.vue";
import changeSteps from "./components/changeSteps.vue";
import countriesApp from "./components/countriesApp.vue";
import FaqAnswers from "./components/FaqAnswers.vue";
import changeMoneyFast from "./components/changeMoneyFast.vue";
import footerSocial from "./components/footerSocial.vue";
export default {
  name: "App",
  components: {
    navigationTop,
    launchApp,
    transferContinue,
    leadingPlatform,
    changeSteps,
    countriesApp,
    FaqAnswers,
    changeMoneyFast,
    footerSocial,
  },
  data() {
    return {
      list: [],
      item: {},
    };
  },
  async mounted() {
    const result = await fetch("list.json");
    const data = await result.json();
    this.list = data;
  },
};
</script>

<style>
@font-face {
  font-family: "TT Firs Neue";
  src: url("./fonts/TTFirsNeue/TTFirsNeue-Light.woff");
  /*src: url("src/fonts/TTFirsNeue/TTFirsNeue-Black.woff"); */
}
body {
  margin: 0;
  overflow-y: auto;
  overflow-x: auto;
  font-family: "TT Firs Neue";
  box-sizing: border-box;
}
.wrapper-all {
  width: 100%;
}
@media screen and (min-width: 721px) {
  body {
    background-color: #f5f9fe;
  }
}
figure {
  margin-block-start: 0;
  margin-block-end: 0;
  margin-inline-start: 0;
  margin-inline-end: 0;
  padding-inline-start: 0;
}
ul {
  margin-block-start: 0;
  margin-block-end: 0;
  margin-inline-start: 0;
  margin-inline-end: 0px;
  padding-inline-start: 0px;
}
h1 {
  font-size: 0;
  margin-block-start: 0;
  margin-block-end: 0;
}
h2 {
  margin-block-start: 0;
  margin-block-end: 0;
}
button:hover {
  background-color: #3474ca;
}
button:active {
  background-color: #295da2;
}
</style>

<style scoped>
p {
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  text-align: left;
  color: #6f767e;
}
@media screen and (min-width: 721px) {
  .wrapper {
    position: relative;
    height: 850px;
  }
  .wrapper-launchApp,
  .wrapper-transferContinue {
    position: absolute;
    width: 100%;
  }
  .wrapper-transferContinue {
    top: 65px;
    height: 485px;
  }
  .wrapper-launchApp {
    top: 520px;
  }
  .wrapper-FaqAnswers {
    background-color: white;
    width: 100%;
    display: flex;
    justify-content: space-between;
    padding: 80px 24px 50px 24px;
  }
  .wrapper-FaqAnswers > h1 {
    font-size: 48px;
    font-weight: 700px;
  }
  .wrapper-FaqAnswers > p {
    font-size: 16px;
    line-height: 24px;
    font-weight: 700px;
    width: 25%;
    display: flex;
    align-items: center;
  }
}
@media screen and (min-width: 1441px) {
  .wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: nowrap;
    height: 815px;
  }
  .wrapper-launchApp,
  .wrapper-transferContinue {
    width: 45%;
  }
  .wrapper-transferContinue {
    position: relative;
  }
  .wrapper-launchApp {
    position: relative;
    top: auto;
  }
  .wrapper-FaqAnswers-large {
    background-color: white;
    display: flex;
    width: 100%;
    padding: 120px 108px;
  }
  .wrapper-FaqAnswers {
    display: flex;
    justify-content: flex-start;
    padding: 0 0;
    flex-direction: column;
    flex-basis: 222px;
  }
  .wrapper-items-large {
    flex-basis: 780px;
    flex-grow: 1;
  }
}
</style>
