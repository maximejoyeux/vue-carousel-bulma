<template>
  <div>
    <link rel="stylesheet">
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
          src: './src/assets/images/sports.1.jpg',
          link: '/',
        },
        {
          title: 'The best image3',
          src: './src/assets/images/sports.1.jpg',
          link: '/',
        },
        {
          title: 'The best image4',
          src: './src/assets/images/sports.1.jpg',
          link: '/',
        },
      ],
    };
  },
};
</script>

