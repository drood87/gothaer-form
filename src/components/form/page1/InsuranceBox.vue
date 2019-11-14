<template>
  <label :for="product.name" class="product">
    <div class="product__desc">
      <h4 class="heading-tertiary">{{product.name}}</h4>
      <p>{{product.desc}}</p>
    </div>
    <div class="product__input">
      <input
        :id="product.name.toLowerCase()"
        class="styled-checkbox"
        type="checkbox"
        name="selectProduct"
        v-on:click="selected"
      />
    </div>
  </label>
</template>

<script>
export default {
  name: "InsuranceBox",
  props: {
    product: Object
  },
  data() {
    return {
      checkedInsurances: []
    };
  },
  methods: {
    selected(ev) {
      // eslint-disable-next-line no-console
      this.$emit("selected", {
        element: ev.target.attributes.id.value,
        newSelection: ev.target.checked
      });
    }
  }
};
</script>

<style lang="scss" scoped>
@import "./../../../styles/components/_insurancebox.scss";
</style>