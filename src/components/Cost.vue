<template>

  <div class="cost">

    <div class="container">

      <div class="cost__header">

        <h3 class="cost__title">Стоимости</h3>

        <button

          class="cost__btn"
          @click="setActive"

        >

          <span

            class="cost__arrow"
            :class=" isActive ? 'cost__arrow_up' :  'cost__arrow_down'"

          />

        </button>

      </div>

    <template v-if="isActive">

      <div

        class="cost__prices price"
        v-for="(value,ind) in costValue"
        :key="ind"

      >

        <div class="price__title">{{ value.title }}</div>

        <div class="price__item">

          <span class="price__square">{{ value.square }}</span>

          <span class="price__total">{{ value.total }}</span>

        </div>

      </div>

    </template>

    </div>

  </div>

</template>

<script>

  export default {

    name: 'Cost',

    props: {

      costValue: {

        type: Array,
        default: () => [],

      }

    },

    data() {

      return {

        isActive: true,

      }

    },

    methods: {

      setActive() {

        this.isActive = !this.isActive

      }
    },

  }

</script>

<style lang="scss" scoped>

  .cost {

    width: 100%;
    padding-left: 8px;
    padding-right: 8px;
    margin-bottom: 8px;

    &__header {

      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;
      padding: 4px 1px 5px 13px;
      border-bottom: 1px solid #EBEDF0;

    }

    &__title {

      line-height: 170.23%;
      text-transform: uppercase;
      margin-right: auto;

    }

    &__btn {

      width: 40px;
      height: 40px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      border: none;
      background-color: #fff;

    }

    &__arrow {

        width: 8px;
        height: 8px;
        border-top: 2px solid #184F90;
        border-right: 2px solid #184F90;

      &_up {

        transform: rotate(-45deg);

      }

      &_down {


        transform: rotate(135deg);

      }

    }

    &__prices {

      padding-left: 2px;
      padding-right: 2px;




    }

    .cost__price.price:nth-child(1) {

      .price__title {

        color: #7650A6;

        }

      }

    .price {

      &__title {


        width: 100%;
        color: #4F5863;
        font-weight: 600;
        padding-top: 6px;
        padding-bottom: 4px;
        padding-left: 14px;

      }

      &__item {

        display: flex;
        flex-flow: row nowrap;
        justify-content: flex-start;
        align-items: center;
        background: #F6F7F8;
        border-radius: 2px;
        padding: 3px 14px 4px;

      }

      &__square {

        font-weight: 600;
        font-size: 16px;
        line-height: 170.23%;
        margin-right: auto;

      }

      &__total {

        font-size: 24px;
        line-height: 41px;

      }

    }

  }

</style>
