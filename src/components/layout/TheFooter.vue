<template>
  <footer class="footer">
    <div class="container">
      <a href="#" class="footer__logo">
        <img src="@/assets/uploads/svg/logo.svg" alt="логотип">
        alpha
      </a>
      <div class="footer__info">
        © alpha, 2023
      </div>
    </div>
  </footer>
</template>

<script>

export default {
  name: 'TheFooter',

  setup() {

  }
}
</script>

<style scoped lang="scss">
.footer {
  background: #F0F6FE;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  width: 100%;
  padding: 64px 0;
  margin-top: 72px;
  @media (max-width: 991px) {
    padding: 30px 0;
  }
}

.footer__logo {
  display: flex;
  align-items: center;
  color: #1D37AF;
  font-size: 30px;
  font-weight: 900;
  line-height: 120%;
  letter-spacing: -2px;

  img {
    width: 43px;
    height: 43px;
    margin-right: 9px;
  }
}

.footer__info {
  color: #81899D;
  font-size: 16px;
  font-weight: 400;
  line-height: 140%;
  margin-top: 10px;
}
</style>
