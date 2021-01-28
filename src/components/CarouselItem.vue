<template>

  <div

    :class="isActivePopup ? 'popup' : ''"
    @click="()=> {this.isActivePopup = !this.isActivePopup}"

  >

    <div class="car_item" >

      <img

        :src="require('../assets/img/slider/' + car_item.img)" alt=""
        @touchstart.prevent="(event)=>touchStart(event)"
        @touchend.prevent="(event)=>touchEnd(event)"

      />

    </div>

  </div>

</template>


<script>

  export default {

    name: 'CarouselItem',

    props: {

      car_item: {

        type: Object,
        default: () => {}

      },

    },

    data: () => {

      return {

        isActivePopup: false,
        curentSlideIndex: 0,
        startTouchX: 0,
        endTouchX: 0,
        startTouchY: 0,
        endTouchY: 0,

      }

    },

    methods: {

      touchStart(event) {

        this.startTouchX = event.changedTouches[0].clientX
        this.startTouchY = event.changedTouches[0].clientY

      },

      touchEnd(event) {

        this.endTouchX = event.changedTouches[0].clientX
        this.endTouchY = event.changedTouches[0].clientY
        this.moveSlide()

      },

      moveSlide() {

        if (this.startTouchX > this.endTouchX && this.curentSlideIndex < 4) {

           this.curentSlideIndex += 1;

        } else if (this.startTouchX < this.endTouchX && this.curentSlideIndex > 0) {

           this.curentSlideIndex -= 1;

        } else if (this.startTouchX - this.endTouchX < 10 && this.startTouchY - this.endTouchY < 10) {

          this.isActivePopup = !this.isActivePopup;

        }

        this.$emit('eventMoveSlide', this.curentSlideIndex)

      },

      onOpenPopup() {

        this.isActivePopup = !this.isActivePopup;

      }

    },

  }
</script>


<style lang="scss" scoped>

  .car_item {

    min-width: 212px;
    height: 291px;

    img {

      width: 100%;

    }

  }

  .popup {

    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.3);
    z-index: 100;
    display: flex;
    justify-content: center;
    padding-top: 50px;

    .car_item {

      min-width: 80%;

    }

  }


</style>
