<template>

  <header class="header">

   <div class="header__container">

     <h1 class="header__title">{{ title }}</h1>

     <div class="header__menu">

       <span></span>
       <span></span>

     </div>

   </div>

  </header>

</template>


<script>

  export default {

    name: 'Header',

    props: {

      title: String,
      default:() => 'Название карточки',

    }

  }

</script>


<style lang="scss" scoped>

  .header {

    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    padding: 12px 0 12px 16px;
    background: #FFFFFF;
    box-shadow: 0px 4px 10px rgba(10, 61, 128, 0.05);
    z-index: 3;

    &__container {

      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;


    }

    &__title {

      font-weight: bold;
      font-size: 18px;
      line-height: 25px;
      margin-right: auto;
      text-transform: uppercase;

    }

    &__menu {

      width: 60px;
      height: 36px;
      border-left: 1px solid #E2E5E9;
      position: relative;

      span {

        width: 12px;
        height: 2px;
        position: absolute;
        top: 17px;
        left: 21.5px;
        background-color: #173456;
        border-radius: 2px;

        &:nth-child(1) {

          transform: rotate(45deg);

        }
        &:nth-child(2) {

          transform: rotate(-45deg);

        }

      }

    }

  }

</style>
