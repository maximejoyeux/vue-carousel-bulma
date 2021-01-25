<template>
  <div>
    <section class="section">
      <div class="container">
        <carousel
          :items="slides"
          :loop="true"
          :infinite="true"
          :slidesToShow="isMobile ? 1 : 3"
          :slidesToScroll="1"
          :pagination="false"
          :navigation="false"
          :navigationSwipe="true"
          :autoplay="true"
          :breakpoints="[]"
        >
          <div slot="item" slot-scope="{ item }">
            <a target="_blank" :href="item.link">
              <div>
                <img :src="item.src" />
                <p class="mt-2">{{ item.title }}</p>
              </div>
            </a>
          </div>
          <!-- <i
            slot="previous"
            class="icon-left-open-big slider-navigation previous"
          ></i>
          <i slot="next" class="icon-right-open-big slider-navigation next"></i> -->
        </carousel>
      </div>
    </section>
  </div>
</template>

<script>
import carousel from './components/bulma-vue-carousel.vue';

export default {
  name: 'app',
  components: {
    carousel,
  },
  data() {
    return {
      slides: [
        {
          title: 'The best image1',
          src: './src/assets/images/sports.1.jpg',
          link: '/',
        },
        {
          title: 'The best image2',
          src: './src/assets/images/sports.2.jpg',
          link: '/',
        },
        {
          title: 'The best image3',
          src: './src/assets/images/sports.3.jpg',
          link: '/',
        },
        {
          title: 'The best image4',
          src: './src/assets/images/sports.5.jpg',
          link: '/',
        },
      ],
    };
  },
};
</script>


<style lang="scss">
@import '~node_modules/bulma-carousel/dist/css/bulma-carousel.min.css';

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
