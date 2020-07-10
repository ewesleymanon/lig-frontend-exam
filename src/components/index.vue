<template>
  <div>
    <header>
      <a href="#" class="logo">Website Logo</a>
    </header>
    <main>
      <article>
        <Slider />
        <section class="main-content">
          <div class="article-wrapper">
            <section
              v-for="(article, index) in articles"
              v-bind:key="index"
              class="article-list"
            >
              <a
                href="https://liginc.co.jp/"
                target="_blank"
                class="article-item"
              >
                <figure>
                  <img
                    :src="`${article.img}`"
                    class="article-item__img"
                    alt="Article Image"
                  />
                </figure>
                <div class="article-item__details">
                  <small class="article-item__date">{{ article.date }}</small>
                  <h3 class="article-item__title">
                    {{ article.title }}
                  </h3>
                  <p class="article-item__description">
                    {{ article.description }}
                  </p>
                </div>
              </a>
            </section>
            <p>
              <a class="btn-more" href="https://liginc.co.jp/" target="_blank">
                More
              </a>
            </p>
          </div>
          <aside class="aside">
            <a href="#">
              <section class="banner">
                Dummy Banner
              </section>
            </a>
            <section class="recommend">
              <h3 class="recommend__title">Recommend</h3>
              <div
                v-for="(article, index) in recommendArticle"
                v-bind:key="index"
                class="recommend-article"
              >
                <a
                  href="https://liginc.co.jp/"
                  target="_blank"
                  class="recommend-article__item"
                >
                  <figure>
                    <img
                      :src="`${article.img}`"
                      class="recommend-article__img"
                      alt="Recommended Article Image"
                    />
                  </figure>
                  <div class="recommend-article__details">
                    <h6 class="recommend-article__title">
                      {{ article.title }}
                    </h6>
                    <small class="recommend-article__date">
                      {{ article.date }}
                    </small>
                  </div>
                </a>
              </div>
            </section>
            <section v-for="index in 3" v-bind:key="index" class="banner-list">
              <a href="#">
                <div class="banner-list__item">Dummy Banner</div>
              </a>
            </section>
          </aside>
          <a href="#" class="top-btn">
            <img
              src="../assets/images/icons/chevron-up.png"
              alt="Back To Top Arrow"
              class="top-btn__icon"
            />
          </a>
        </section>
      </article>
    </main>
    <footer>
      <div class="footer-content">
        <div class="footer-content__nav">
          <a href="#">運営会社</a>
          <a href="#">個人情報保護について</a>
        </div>
        <p>©2016 Sample</p>
      </div>
    </footer>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Slider from "./slider/slider.vue";

@Component({
  components: {
    Slider
  }
})
export default class Home extends Vue {
  private articles: Array<object> = [
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article2.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    },
    {
      img: require("../assets/images/article-images/ph-article1.jpg"),
      date: "2016.01.01",
      title:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト",
      description:
        "サンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキストサンプルテキスト"
    }
  ];

  get recommendArticle(): Array<object> {
    const recommendedArticles = this.articles.slice(2, 5);
    return recommendedArticles;
  }
}
</script>
