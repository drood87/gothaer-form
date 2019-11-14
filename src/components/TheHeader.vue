<template>
  <header class="header">
    <div class="header__logo-container header__logo-container--bmw">
      <img class="header__logo" src="./../assets/bmw-logo.png" alt="BMW Logo" />
    </div>
    <div class="header__logo-container header__logo-container--gothaer">
      <p>präsentiert von</p>
      <img
        class="header__logo header__logo--gothaer"
        src="./../assets/gothaer-logo.png"
        alt="Gothaer Logo"
      />
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style lang="scss" scoped>
@import "./../styles/components/_header.scss";
</style>