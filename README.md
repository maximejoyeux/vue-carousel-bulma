# vue-carousel-bulma
A VueJs carousel component build with Bulma

## Example
```
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
```

### Named Slots
* **item**: used to draw carousel item provided as `item` in in the slot-scope. (see example above)
* **previous**: slot to draw the previous icon
* **next**: slot to draw the next icon

### Props
```
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
```
