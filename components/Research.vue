<template>
  <div id="research">
    <div class="container">
      <h1 class="title is-1">
        Research
      </h1>
      <p class="is-size-4">
        Works published in academic journals.
      </p>
      <hr>
      <br>
      <div v-for="item in sciencepapers" :key="item.title">
        <section class="hero">
          <h1 class="subtitle">
            {{ item.year }}
          </h1>
          <h1 class="title is-5">
            {{ item.title }}
          </h1>
          <h2 class="subtitle">
            Journal: {{ item.journal }} <br>DOI:
            <a :href="'https://doi.org/' + item.doi">{{ item.doi }}</a>
          </h2>
          <hr>
        </section>
        <br>
      </div>
    </div>
  </div>
</template>
<script>
import sciencepapers from '../../public/var/publications.json'
export default {
  data () {
    return {
      sciencepapers
    }
  }
}
</script>
