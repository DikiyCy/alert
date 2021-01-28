<template>

  <div class="upward">

    <div class="container">

      <h3 class="upward__title">Прогнозируемое повышение на</h3>

      <span class="upward__total">{{ upperPrice }}</span>

    </div>

  </div>

</template>

<script>

  export default {

    name: 'UpwardPrice',

    props: {

      upperPrice: {

        type: String,
        default: () => '0 p.'

      }
    }

  }

</script>

<style lang="scss" scoped>

  .upward {

    width: 100%;
    padding-left: 8px;
    padding-right: 8px;

    .container {

      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-self: center;
      padding: 8px 16px;
      margin-bottom: 24px;

    }

    &__title {

      font-size: 12px;
      margin-right: auto ;

    }

    &__total {

      font-weight: 600;
      font-size: 14px;
      color: #184F90;

    }

  }

</style>
