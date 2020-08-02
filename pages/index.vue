<template>
  <div id="home">
    <div class="container">
      <section class="section">
        <div id="main-picture" class="container">
          <figure class="image">
            <img
              id="henrique"
              class="is-rounded"
              src="../assets/imgs/henrique-gomide.jpg"
            >
          </figure>
          <h1 class="title text-centered">
            Henrique Gomide, Ph.D.
          </h1>
          <h2 class="subtitle">
            Assistant Professor and Data Scientist
          </h2>

          <div id="social-network" class="columns">
            <div class="column is-half is-offset-one-quarter">
              <a
                href="https://github.com/henriquepgomide"
              ><img
                class="is-rounded logo"
                src="~assets/icons/github.svg"
              ></a>
              <a
                href="https://www.linkedin.com/in/hpgomide/"
              ><img
                class="is-rounded logo"
                src="~assets/icons/linkedin.svg"
              ></a>
              <a
                href="https://www.youtube.com/c/HenriqueGomide/"
              ><img
                class="is-rounded logo"
                src="~assets/icons/youtube.svg"
              ></a>
            </div>
          </div>
        </div>
      </section>

      <div class="container">
        <br>
        <h1 class="title">
          <router-link to="/blog">
            Blog & Tutorials
          </router-link>
        </h1>
        <p class="subtitle">
          Tips on Data Science and Machine Learning
        </p>
        <ol>
          <div
            v-for="(post, index) in posts"
            :key="post.slug + '_' + index"
            class="column"
          >
            <li class="subtitle papers">
              <b><router-link :to="'/blog/' + post.slug">{{
                post.title
              }}</router-link></b>. {{ post.summary }}
              <router-link :to="'/blog/' + post.slug">
                Read
              </router-link>
            </li>
          </div>
          <li class="subtitle papers">
            <router-link to="/blog">
              <b>Go to Blog...</b>
            </router-link>
          </li>
        </ol>
      </div>

      <br>

      <div class="container">
        <br>
        <h1 class="title">
          <router-link to="/research">
            Research
          </router-link>
        </h1>
        <p class="subtitle">
          Get to know my research projects and papers. Latest publications:
        </p>
        <ol>
          <div
            v-for="item in sciencepapers"
            :key="item.title"
          >
            <li class="subtitle papers">
              <b>{{ item.title }} </b>. {{ item.journal }}. DOI:
              <a :href="'https://doi.org/' + item.doi">{{ item.doi }}</a>.
            </li>
          </div>
          <li class="subtitle papers">
            <router-link to="/research">
              <b>Go to research...</b>
            </router-link>
          </li>
        </ol>
      </div>
    </div>
  </div>
</template>
<script>
import { butter } from '~/plugins/buttercms'

export default {
  name: 'BlogHome',
  async asyncData ({ $content }) {
    const sciencepapers = await $content('publications').fetch()
    return {
      sciencepapers
    }
  },
  data () {
    return {
      page_title: 'Blog',
      posts: []
    }
  },
  created () {
    this.getPosts()
  },
  methods: {
    getPosts () {
      butter.post
        .list({
          page: 1,
          page_size: 3
        })
        .then((res) => {
          this.posts = res.data.data
        })
    }
  }
}
</script>

<style scoped>
#henrique {
  width: 240px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  padding-bottom: 20px;
}

#main-picture {
  text-align: center;
}

.logo {
  width: 50px;
}

.logo:hover {
  filter: invert(53%) sepia(69%) saturate(5720%) hue-rotate(340deg)
    brightness(102%) contrast(105%);
}

.papers {
  margin-left: 3em;
  padding-top: 0.7em;
}
</style>
