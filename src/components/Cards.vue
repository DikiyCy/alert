<template>

  <section class="card">

    <Header title = "Карточка квартиры"/>

    <div class="card__container">

      <div class="card__info">

        <span class="card__number">№{{ "12" }}</span>

        <span class="card__meter" > М </span>

        <span class="card__square">{{ "59.52м²" }}</span>

        <div class="card__state">{{ "Свободно" }}</div>

      </div>

      <ul class="card__links">

        <li

          v-for="(linkItem, ind) in linkValue"
          :key="linkItem.id"
          @click="setPage(linkItem.id)"

        >

          <h2

            class="card__link"
            :class=" !!activeLink[ind] ? 'active' : 'not_active' "
            :check="activeLink[ind]"

          >

            {{ linkItem.text }}

          </h2>

        </li>

      </ul>

      <template

        v-if="activePage === 1"

      >

        <Slider />

        <Cost :costValue="costValue"/>

        <UpwardPrice :upperPrice="upperPrice"/>

        <div class="card__wrap card__wrap_1">

          <CardDetail

            v-for="(item, ind) in 3"
            :key="ind"
            :detail="cardDetail[ind]"

          />

        </div>

        <div class="card__wrap card__wrap_2">

          <CardDetail

            v-for="(item, ind) in 2"
            :key="ind"
            :detail="cardDetail[ind + 3]"

          />

        </div>

      </template>

    </div>

    <Footer />

  </section>

</template>


<script>

  import Header from './Header.vue';
  import Slider from './Slider.vue';
  import Cost from './Cost.vue';
  import CardDetail from './CardDetail.vue';
  import UpwardPrice from './UpwardPrice.vue';
  import Footer from './Footer.vue';

  let nextLink = 1;

  export default {

    name: 'Cards',
    components: {

      Header,
      Slider,
      Cost,
      CardDetail,
      UpwardPrice,
      Footer,

    },

    data () {

      return {

        linkValue: [

          {
            id: nextLink++,
            text: 'Информация'
          },

          {
            id: nextLink++,
            text: 'Площади'
          },

          {
            id: nextLink++,
            text: 'Акции'
          },

          {
            id: nextLink++,
            text: 'Преимущества'
          }

        ],

        costValue: [
          {
            title: 'С акцией месяца',
            square: '79 015 р./м²',
            total: '3 870 900р.',
          },
          {
            title: '100% / ипотека',
            square: '79 015 р./м²',
            total: '3 870 900р.',
          },
          {
            title: 'Базовая',
            square: '79 015 р./м²',
            total: '3 870 900р.',
          },
        ],

        cardDetail: [
          {
            title: 'Подъезд',
            value: '17',
          },
          {
            title: 'Этаж',
            value: '17',
          },
          {
            title: 'Комнат',
            value: '17',
          },
          {
            title: 'Высота потолка',
            value: '2.76м²',
          },
          {
            title: 'Вид из окна',
            value: 'Во двор и на улицу',
          },
        ],

        activePage: 1,

        upperPrice: '120 321р.',

        activeLink: [

          1,
          0,
          0,
          0,

        ]

      }
    },

    methods: {

      setPage(id) {

        for (let i = 0; i < this.linkValue.length; i++ ) {

          this.activeLink.shift();

          if (i === id - 1) {

            this.activeLink.push(1)

          } else {

            this.activeLink.push(0)

          }

        }

        return  this.activePage = id

      }

    }
  }

</script>

<style lang="scss">

  .card {

    width: 100%;
    min-height: 100vh;
    height: 100%;

    button {

      outline: transparent;

    }

    ::-webkit-scrollbar {
      height:0px;
      width: 0px;
    }

    .container {

      background-color: #fff;
      box-shadow: 0px 4px 10px rgba(10, 61, 128, 0.05);
      border-radius: 3px;
      padding-bottom: 2px;

    }

    &__container {

      width: 100%;
      min-height: 100vh;
      position: relative;
      padding-top: 60px;
      background: #E5E5E5;
      margin-right: 8px;
      padding-bottom: 71px;

    }

    &__info {

      width: 100%;
      min-height: 49px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;
      padding: 8px;
      background-color: #fff;
      border-bottom: 1px solid #E5E5E5;

    }

    &__number, &__meter, &__square {

      background: #FFFFFF;
      border: 1px solid #E2E5E9;
      line-height: 170.23%;

    }

    &__number {

      border-radius: 3px;
      padding: 4px 8px;
      margin-right: 4px;

    }

    &__meter {

      padding: 4px 7px 4px 9px;
      border-top-left-radius: 3px;
      border-bottom-left-radius: 3px;

    }

    &__square {

      padding: 4px 8px 4px 9px;
      border-left: none;
      border-top-right-radius: 3px;
      border-bottom-right-radius: 3px;
      margin-right: auto;

    }

    &__state {

      width: 80px;
      height: 24px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      background: #44A86E;
      border-radius: 32px;

      font-size: 12px;
      line-height: 20px;
      text-align: center;
      color: #FFFFFF;

    }

    &__links {

      width: 100%;
      min-height: 44px;
      display: flex;
      justify-content: flex-start;
      align-items: center;
      background: #fff;
      overflow-x: scroll;
      overflow-y: hidden;
      padding-left: 8px;
      margin-bottom: 8px;
      scrollbar-width: none;

    }

    &__link {

      padding: 8px 16px;
      position: relative;
      display: block;

      &.active, &.not_active {

        &::before {

          content: '';
          position: absolute;
          bottom: -2px;
          left: 0;
          width: 100%;
          height: 2px;
          background: #184F90;
          border-radius: 1px 1px 0px 0px;

        }

      }

      &.not_active {

        color: #7C8A9D;

        &::before {

          background: #FFF;

        }

      }

    }

    &__wrap {

      display: flex;
      flex-flow: row wrap;
      justify-content: space-between;
      align-items: center;
      padding-left: 8px;
      padding-right: 8px;
      margin-bottom: 8px;

      &_1 {

        .detail {

          flex: 0 0 calc(33.3% - 6px);

          &:nth-child(2) {

            margin: 0 8px;
          }

        }

      }

      &_2 {



        .detail {

          flex: 0 0 calc(50% - 4px);

          &:nth-child(2) {

            margin-left: 8px;

          }

        }

      }

    }

  }

</style>
