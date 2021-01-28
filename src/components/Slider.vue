<template>

  <div class="slider">

    <div class="container">

      <div class="slider__wrap" >

        <Carousel

          :carousel="sliderItems"
          @setPage="setPage"

        />

      </div>

      <div class="slider__dots">

        <span

          v-for="(img, ind) in 5"
          :key="ind"
          class="slider__dot not-active"
          :class="activeDot[ind] === 1 ? 'active' : 'not-active' "
          :chek="activeDot[ind]"

        />

      </div>

    </div>


  </div>

</template>

<script>

  import Carousel from './Carousel';

  export default {

    name: 'Slider',
    
    components: {

      Carousel

    },

    data () {

      return {

        sliderItems: [

          { id: 1, name: 'img1', img: 'img-1.png'},
          { id: 2, name: 'img2', img: 'img-2.jpg'},
          { id: 3, name: 'img3', img: 'img-3.jpg'},
          { id: 4, name: 'img4', img: 'img-4.jpg'},
          { id: 5, name: 'img5', img: 'img-5.jpg'},

        ],

        activeDot: [

          1,
          0,
          0,
          0,
          0,

        ]

      }
    },

    methods: {

      setPage(id) {

        for (let i = 0; i < this.activeDot.length; i++ ) {

          this.activeDot.shift();

          if (i === id ) {

            this.activeDot.push(1)

          } else {

            this.activeDot.push(0)

          }

        }

      }

    }

  }

</script>

<style lang="scss" scoped>

  .slider {

    width: 100%;
    padding-left: 8px;
    padding-right: 8px;

    .container {

      margin-bottom: 24px;
      padding: 16px 16px 0px;

      border: 1px solid #E2E5E9;
      border-radius: 3px;
      padding-top: 18px;

    }

    &__wrap {


      border: 1px solid #E2E5E9;
      border-radius: 3px;
      padding-top: 18px;
      padding-bottom: 18px;


    }

    &__show {

      width: 212px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;
      overflow-x: auto;
      scroll-snap-type: x mandatory;
      margin: 0 auto;
      scrollbar-width: none;


    }

    &__img {

      min-width: 212px;
      height: 291px;
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      scroll-snap-align: start;

    }

    &__dots {

      height: 16px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;

    }

    &__dot {

      width: 4px;
      height: 4px;
      border-radius: 100%;
      margin: 0 2px;

      &.not-active {

        background: #C5CBD3;

      }

      &.active {

        background: #184F90;

      }

    }

  }

</style>
