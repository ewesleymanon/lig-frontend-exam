<template>
  <section class="slides">
    <transition-group tag="div" :name="transitionName" class="slides-group">
      <div
        v-if="show"
        :key="current"
        class="slide"
        :style="{ backgroundImage: `url(${list[current].img})` }"
      >
        <div class="slide__content">
          <h3 class="slide__title">{{ list[current].title }}</h3>
          <p class="slide__description">{{ list[current].desc }}</p>
        </div>
      </div>
    </transition-group>
    <!-- Slider Button | Next, Prev -->
    <div class="slider-buttons">
      <img
        class="prev"
        @click="slide(-1)"
        src="../../assets/images/icons/chevron-left.png"
        alt="Left Arrow"
      />
      <img
        class="next"
        @click="slide(1)"
        src="../../assets/images/icons/chevron-right.png"
        alt="Right Arrow"
      />
    </div>
    <!-- Pagers -->
    <ul class="dots">
      <li
        v-for="(dot, index) in list"
        v-bind:key="index"
        :class="{ active: index === current }"
        @click="jump(index)"
      ></li>
    </ul>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class Slider extends Vue {
  private show = false;
  private direction = 1;
  private current = 0;
  private transitionName = "fade";

  private list: Array<object> = [
    {
      id: 1,
      img: require("../../assets/images/slider-images/slider-img1.jpg"),
      title: "キャッチコピーが入ります。",
      desc:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト "
    },
    {
      id: 2,
      img: require("../../assets/images/slider-images/slider-img2.jpg"),
      title: "キャッチコピーが入ります。",
      desc:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      id: 3,
      img: require("../../assets/images/slider-images/slider-img3.jpg"),
      title: "キャッチコピーが入ります。",
      desc:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    }
  ];

  public jump(index: number): void {
    if (this.current < index) {
      this.transitionName = "slide-next";
    } else {
      this.transitionName = "slide-prev";
    }
    this.current = index;
  }

  public slide(dir: number): void {
    this.direction = dir;
    dir === 1
      ? (this.transitionName = "slide-next")
      : (this.transitionName = "slide-prev");
    const len = this.list.length;
    this.current = (this.current + (dir % len) + len) % len;
  }

  mounted() {
    this.show = true;
  }
}
</script>
