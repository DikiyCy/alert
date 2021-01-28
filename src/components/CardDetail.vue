<template>

  <div class="detail">

    <div class="container">

      <h3 class="detail__title">{{ detail.title }}</h3>

      <h4 class="detail__value">{{ detail.value }}</h4>

    </div>

  </div>

</template>

<script>

  export default {

    name: 'CardDetail',
    props: {
      detail: {
        type: Object,
        require: true,
      }
    }

  }

</script>

<style lang="scss" scoped>

  .detail {

    max-width: 250px;

    .container {

      padding-left: 2px;
      padding-right: 2px;

    }

    &__title, &__value {

      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      line-height: 170.23%;

    }

    &__title {

      font-size: 14px;
      padding-top: 4px;
      padding-bottom: 4px;
      text-align: center;

    }

    &__value {

      background: #F6F7F8;
      border-radius: 2px;
      padding-top: 8px;
      padding-bottom: 8px;
      text-align: center;

    }

  }

</style>
