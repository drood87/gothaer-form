<template>
  <div>
    <Header />
    <form>
      <div v-show="step == 1">
        <h1 class="heading-primary">Betriebliche Gesundheitsfoerderung</h1>
        <InsuranceSelect />
      </div>
      <div v-show="step == 2">
        <h2>Step 2</h2>
      </div>
    </form>
    <div class="button-wrapper" @click="next">
      <ButtonPrevNext />
    </div>
  </div>
</template>

<script>
import Header from "./components/TheHeader";
import InsuranceSelect from "./components/form/page1/InsuranceSelect";
import ButtonPrevNext from "./components/Button";

export default {
  name: "app",
  components: {
    Header,
    InsuranceSelect,
    ButtonPrevNext
  },
  data() {
    return {
      step: 1
    };
  },
  methods: {
    prev() {
      this.step--;
    },
    next() {
      this.step++;
    }
  }
};
</script>

<style lang="scss">
.button-wrapper {
  display: inline-block;
}
</style>
