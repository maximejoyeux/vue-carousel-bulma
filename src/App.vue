<template>
  <div>
    <section class="section">
      <div class="container">
        <carousel
          :items="slides"
          :loop="true"
          :infinite="true"
          :slidesToShow="3"
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
          <i
            slot="previous"
            class="icon-left-open-big slider-navigation previous"
          ></i>
          <i slot="next" class="icon-right-open-big slider-navigation next"></i>
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
