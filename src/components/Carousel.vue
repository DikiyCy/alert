<template>

  <div class="wrapp">

    <div

      class="carousel"
      :style="{ 'margin-left': '-' + (100 * activeSlide) + '%' }"

    >

      <CarouselItem

        v-for="item in carousel"
        :key="item.id"
        :car_item="item"
        @eventMoveSlide="onMoveSlide"

      />

    </div>

  </div>


</template>

<script>

  import CarouselItem from './CarouselItem.vue';

export default {

  name: 'Carousel',

  components: {

    CarouselItem,

  },

  props:{

    carousel: {

      type: Array,
      default: () => []

    },

  },

  data(){

    return{

      activeSlide: 0,

      activeDot: [

        1,
        0,
        0,
        0,
        0,

      ],

    }

  },

  methods: {

    onMoveSlide(count) {

      this.activeSlide = count;
      this.$emit('setPage', count);

    },

  },

}
</script>

<style lang="scss" scoped>

  .wrapp {

    max-width: 212px;
    overflow: hidden;
    margin: 0 auto;

  }

  .carousel {
    
    display: flex;
    transition: all ease .5s;

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
