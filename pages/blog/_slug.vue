<template>
  <div id="blog-post">
    <div class="container is-large">
      <section class="section">
        <div class="content is-medium">
          <h1 class="title">
            {{ post.data.title }}
          </h1>
          <h4 class="details subtitle">
            {{ post.data.author.first_name }} {{ post.data.author.last_name }}
          </h4>
          <div class="addthis_inline_share_toolbox" />
        </div>
      </section>

      <div class="content is-medium">
        <section class="section">
          <div v-html="post.data.body" />
        </section>
      </div>

      <section class="section">
        <div class="content is-medium">
          <h1 class="subtitle is-2">
            Other posts
          </h1>
          <nav class="pagination" role="navigation" aria-label="pagination">
            <a class="pagination-previous" title="This is the first page">
              <router-link
                v-if="post.meta.previous_post"
                :to="/blog/ + post.meta.previous_post.slug"
              >
                {{ post.meta.previous_post.title }}
              </router-link>
            </a>
            <a class="pagination-next">
              <router-link
                v-if="post.meta.next_post"
                :to="/blog/ + post.meta.next_post.slug"
              >
                {{ post.meta.next_post.title }}
              </router-link>
            </a>
          </nav>
        </div>
      </section>
    </div>
  </div>
</template>
<script>
import { butter } from '~/plugins/buttercms'

export default {
  name: 'BlogPost',
  data () {
    return {
      post: {
        data: {
          author: {
          }
        },
        meta: {}
      }
    }
  },
  watch: {
    $route (to, from) {
      this.getPost()
    }
  },
  created () {
    this.getPost()
  },
  methods: {
    getPost () {
      butter.post
        .retrieve(this.$route.params.slug)
        .then((res) => {
          this.post = res.data
        })
        .catch((res) => {
          console.log(res)
        })
    }
  }
}
</script>
<style scoped>
.details {
  padding-top: 10px;
}
</style>
