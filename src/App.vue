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
          title: 'image 1',
          src: 'http://placehold.it/400x300',
          link: '/',
        },
        {
          title: 'image 2',
          src: 'http://placehold.it/400x300',
          link: '/',
        },
        {
          title: 'image 3',
          src: 'http://placehold.it/400x300',
          link: '/',
        },
        {
          title: 'image 4',
          src: 'http://placehold.it/400x300',
          link: '/',
        },
      ],
    };
  },
};
</script>

