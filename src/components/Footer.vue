<template>

  <footer class="footer">

    <div class="footer__container">

      <div class="footer__bg">

        <div class="footer__first"/>

        <div class="footer__beetwen"/>

        <div class="footer__second"/>

      </div>

      <div class="footer__wrap" >

      <template v-for="(btn, ind) in 5" >

        <button class="footer__btn btn" :key="ind" >

          <div :class="`btn__icon btn__icon_${ind + 1}`" />


        </button>

        <div v-if="ind <= 2" class="footer__wand" :key="ind + 20"/>

      </template>

      </div>

    </div>

    <div class="footer__line" />

  </footer>

</template>

<script>

  export default {

    name: 'Footer',

  }

</script>

<style lang="scss" scoped>

  .footer {

    width: 100%;
    position: fixed;
    bottom: 0;
    left: 0;

    &__container {

      height: 70px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;
      margin-left: -10px;
      margin-right: -10px;
      background-position-y: -3px;
      background-position-x: center;
      background-repeat: no-repeat;
      background-size: cover;
      z-index: 3;
      position: relative;

    }

    &__bg {

      width: 100%;
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      align-items: center;
      position: absolute;
      left: 0;
      bottom: 0;

    }

    &__first {

      width: 72px;
      height: 80px;
      background-repeat: no-repeat;
      background-position-x: 0px;
      background-position-y: -3px;
      background-image: url(../assets/img/footer/footer-bg.svg);
      z-index: 10;

    }

    &__beetwen {

      width: calc(100% - 72px - 110px);
      height: 61.8px;
      background-color: #FFFFFF;
      box-shadow: 0px -4px 10px rgba(10, 61, 128, 0.05);
      transform: translateY(0.5%);
      z-index: 8;

    }

    &__second {

      width: 110px;
      height: 80px;
      background-repeat: no-repeat;
      background-position-x: 100%;
      background-position-y: -3px;
      background-image: url(../assets/img/footer/footer-bg.svg);
      z-index: 10;

    }

    &__wrap {

      width: 100%;
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      align-items: center;
      z-index: 20;
      padding-right: 90px;
      padding-left: 10px;

    }

    &__wand {

      width: 1px;
      height: 16px;
      background: #F0F2F4;
      border-radius: 4px;

    }

    &__btn {

      width: 68px;
      height: 44px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      border: none;
      background-color: #fff;

      &:nth-last-child(1) {

        width: 50px;
        height: 50px;
        border-radius: 100%;
        position: absolute;
        top: -25px;
        right: 35px;


      }

      .btn {

        &__icon {

          background-position: center;
          background-repeat: no-repeat;
          background-size: cover;

          &_1 {

            width: 2px;
            height: 15px;
            background-image: url(../assets/img/footer/1-icon.svg);

          }

          &_2 {

            width: 16px;
            height: 14px;
            background-image: url(../assets/img/footer/2-icon.svg);

          }

          &_3 {

            width: 18px;
            height: 16px;
            background-image: url(../assets/img/footer/3-icon.svg);

          }

          &_4 {

            width: 20px;
            height: 20px;
            background-image: url(../assets/img/footer/4-icon.svg);

          }

          &_5 {

            width: 20px;
            height: 20px;
            background-image: url(../assets/img/footer/5-icon.svg);

          }

        }

      }

    }

    &__line {

      position: absolute;
      width: 100%;
      height: 20px;
      bottom: 0;
      left: 0;
      background-color: #ffffff;
      z-index: 15;

    }

  }

</style>
