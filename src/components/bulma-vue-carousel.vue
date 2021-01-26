<template>
  <div class="container">
    <div ref="carousel" class="carousel is-clipped">
      <div class="slide" v-for="(item, index) in items" :key="item.title">
        <slot name="item" :item="item" :index="index"></slot>
      </div>
    </div>
    <a class="carousel-arrow" @click="carousel.previous()">
      <slot name="previous"></slot>
    </a>
    <a class="carousel-arrow" @click="carousel.next()">
      <slot name="next"></slot>
    </a>
  </div>
</template>

<script>
import BulmaCarousel from 'bulma-carousel';

export default {
  props: {
    items: [Object, Array],
    initialSlide: {
      type: Number,
      required: false,
      default: 0,
    },
    slidesToScroll: {
      type: Number,
      required: false,
      default: 1,
    },
    slidesToShow: {
      type: Number,
      required: false,
      default: 1,
    },
    navigation: {
      type: Boolean,
      required: false,
      default: true,
    },
    navigationKeys: {
      type: Boolean,
      required: false,
      default: true,
    },
    navigationSwipe: {
      type: Boolean,
      required: false,
      default: true,
    },
    pagination: {
      type: Boolean,
      required: false,
      default: true,
    },
    loop: {
      type: Boolean,
      required: false,
      default: false,
    },
    infinite: {
      type: Boolean,
      required: false,
      default: false,
    },
    effect: {
      type: String,
      required: false,
      default: 'translate',
    },
    duration: {
      type: Number,
      required: false,
      default: 300,
    },
    timing: {
      type: String,
      required: false,
      default: 'ease',
    },
    autoplay: {
      type: Boolean,
      required: false,
      default: false,
    },
    autoplaySpeed: {
      type: Number,
      required: false,
      default: 3000,
    },
    pauseOnHover: {
      type: Boolean,
      required: false,
      default: true,
    },
    breakpoints: {
      type: Array,
      required: false,
      default: [],
    },
  },
  data() {
    return {
      carousel: null,
      customClass: null,
    };
  },
  mounted() {
    const tag = this.$refs.carousel;

    this.carousel = new BulmaCarousel(tag, {
      slidesToScroll: this.slidesToScroll,
      slidesToShow: this.slidesToShow,
      loop: this.loop,
      initialSlide: this.initialSlide,
      slidesToScroll: this.slidesToScroll,
      slidesToShow: this.slidesToShow,
      navigation: this.navigation,
      navigationKeys: this.navigationKeys,
      navigationSwipe: this.navigationSwipe,
      pagination: this.pagination,
      loop: this.loop,
      infinite: this.infinite,
      effect: this.effect,
      duration: this.duration,
      timing: this.timing,
      autoplay: this.autoplay,
      autoplaySpeed: this.autoplaySpeed,
      pauseOnHover: this.pauseOnHover,
      breakpoints: this.breakpoints,
    });

    this.$on('hook:beforeDestroy', this.destroyCarousel);
  },
  methods: {
    destroyCarousel() {
      if (!this.carousel) return;

      this.carousel.destroy();
      this.carousel = null;
    },
  },
  beforeDestroy() {
    this.carousel.destroy();
    this.carousel = null;
  },
};
</script>


<style lang="scss">

// CUSTOM CARROUSEL STYLE
.slider-navigation {
  font-size: 20px;
  background: transparent;
  position: absolute;
  top: 50%;
  margin-top: -20px;
  cursor: pointer;
  @media only screen and (max-width: 768px) {
    display: none;
  }
}
.slider-navigation.previous {
  left: -2.5%;
}
.slider-navigation.next {
  right: -2.5%;
}
.slider-navigation-previous,
.slider-navigation-next {
  display: none;
}
// Arrows
.icon-left-open-big,
.icon-right-open-big {
  font-size: 20px;
}
</style>
