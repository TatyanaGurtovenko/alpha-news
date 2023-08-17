<template>
  <header class="header">
    <div class="container">
      <a href="#" class="header__logo">
        <img src="@/assets/uploads/svg/logo.svg" alt="логотип">
        alpha
      </a>
    </div>
  </header>
</template>

<script>

export default {
  name: 'TheHeader',

  setup () {

  }
}
</script>

<style scoped lang="scss">
.header {
  background: #FFF;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  width: 100%;
  padding: 40px 0;
  @media (max-width: 991px) {
    padding: 20px 0;
  }
}
.header__logo {
  display: flex;
  align-items: center;
  color: #1D37AF;
  font-size: 40px;
  font-weight: 900;
  line-height: 120%;
  letter-spacing: -2px;
  @media (max-width: 991px) {
    font-size: 30px;
  }
  img {
    width: 43px;
    height: 43px;
    margin-right: 9px;
  }
}
</style>
