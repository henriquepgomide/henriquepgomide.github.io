<template>
  <div id="blog">
    <div class="container">
      <h1 class="title is-1">
        Blog & Tutorials
      </h1>
      <p class="is-size-4">
        Tips on Data Science and Machine Learning
      </p>
    </div>

    <section class="section">
      <div class="container">
        <div v-for="(post, index) in posts" :key="post.slug + '_' + index">
          <router-link :to="'/blog/' + post.slug">
            <div class="columns is-mobile">
              <article class="media">
                <div class="column is-2">
                  <figure class="image">
                    <img
                      v-if="post.featured_image"
                      :src="post.featured_image"
                      alt=""
                    >
                    <img
                      v-else
                      src="http://via.placeholder.com/150x150"
                      alt=""
                    >
                  </figure>
                </div>
                <div class="column">
                  <p>
                    Published on
                    {{ post.published.split("-")[2].substring(0, 2) }}/{{
                      post.published.split("-")[1]
                    }}/{{ post.published.split("-")[0] }}.
                  </p>
                  <h1 class="title">
                    {{ post.title }}
                  </h1>
                  <p class="subtitle">
                    {{ post.summary }}<br>
                  </p>
                </div>
              </article>
            </div>
          </router-link>
          <hr>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <nav class="pagination" role="navigation" aria-label="pagination">
          <a class="pagination-previous" @click="goPage(-1)">Previous</a>
          <a class="pagination-next" @click="goPage(+1)">Next page</a>
          <ul class="pagination-list">
            <li>
              <a
                class="pagination-link is-current"
                aria-label="Page 46"
                aria-current="page"
              >{{ page_number }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </section>
  </div>
</template>
<script>
import { butter } from '~/plugins/buttercms'

export default {
  name: 'BlogHome',
  data () {
    return {
      page_number: 1,
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
          page: this.page_number,
          page_size: 10
        })
        .then((res) => {
          this.posts = res.data.data
        })
    },
    goPage (num) {
      if (this.page_number > 0) {
        this.page_number += num
        this.getPosts()
      } else {
        this.page_number = 1
        this.getPosts()
      }
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
}
</style>
