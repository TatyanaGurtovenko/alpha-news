<template>
  <div class="page-title">
    <div class="container">
      <h1>Новости</h1>
    </div>
  </div>
</template>

<script>


export default {
  name: 'PageTitle',

  setup () {

  }
}
</script>

<style scoped lang="scss">
.page-title {
  background-image: url("@/assets/uploads/images/news-bg.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  height: 320px;
  display: flex;
  align-items: flex-end;
  text-align: left;
  padding: 48px 0;

  @media (max-width: 991px) {
    background-position: 65%;
  }
  h1 {
    color: #17171A;
    font-size: 40px;
    font-weight: 700;
    line-height: 120%;
    letter-spacing: -0.4px;
    @media (max-width: 991px) {
      font-size: 30px;
    }
  }
}
</style>
