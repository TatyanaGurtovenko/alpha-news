<template>
  <a href="" class="button__more">Загрузить ещё</a>
</template>

<script>
export default {
  name: 'MoreButton'
}
</script>

<style scoped lang="scss">
.button__more {
  color: #002DBF;
  text-align: center;
  font-size: 20px;
  font-weight: 600;
  line-height: 120%;
  letter-spacing: -0.2px;
  padding: 16px 32px;
  border-radius: 8px;
  border: 1px solid #002DBF;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: 0.2s;
  &:hover {
    box-shadow: 0px 5px 15px 0px rgba(0, 0, 0, 0.15);
  }
  @media (max-width: 991px) {
    font-size: 16px;
  }
}
</style>
