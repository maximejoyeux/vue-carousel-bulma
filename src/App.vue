<template>
  <div>
    <section class="section">
      <div class="container">
        <carousel
            :items="images"
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
      images: [
        {
          title: 'The best image1',
          src: './src/assets/images/sports.1.jpg',
          desc:
            'Laboris ullamco nostrud qui consectetur aute eiusmod irure aliquip veniam aliquip ut officia laboris amet. Consequat id excepteur mollit dolor fugiat labore. Commodo nulla minim eu commodo reprehenderit veniam eu aliqua aute cillum proident nostrud veniam. Anim voluptate nulla adipisicing in ullamco irure. Velit nostrud ad in duis ex minim nulla cupidatat duis esse nostrud ex ad exercitation. Duis ut do laborum commodo Lorem sunt aliqua labore ex occaecat aliqua nulla id.',
          other: ``,
        },
        {
          title: 'The best image2',
          src: './src/assets/images/sports.2.jpg',
          desc:
            'Non fugiat veniam ipsum Lorem anim sit culpa Lorem. Tempor culpa enim adipisicing nostrud exercitation cillum ex dolore dolor mollit irure enim velit commodo. Labore veniam esse incididunt consequat voluptate esse veniam deserunt excepteur. Lorem labore aute labore voluptate. Enim esse eu consectetur ex fugiat aliqua. Quis dolor amet nostrud ea.',
          other: ``,
        },
        {
          title: 'The best image3',
          src: './src/assets/images/sports.3.jpg',
          desc:
            'Ex in amet amet ea tempor nisi in commodo ullamco exercitation ea qui eiusmod.',
          other: ``,
        },
        {
          title: 'The best image4',
          src: './src/assets/images/sports.5.jpg',
          desc:
            'Sunt amet nisi non non excepteur amet occaecat nulla occaecat deserunt excepteur. Culpa occaecat nulla nulla ea ea. Non occaecat veniam elit in commodo ex esse ipsum occaecat cillum fugiat consequat. Aliquip laborum cupidatat elit in commodo commodo ea. Id esse labore adipisicing proident adipisicing anim sint exercitation nostrud velit. Veniam aliqua magna enim do.',
          other: ``,
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
// END CUSTOM CARROUSEL STYLE
</style>
