<template>
  <div id="headercomp">
    <b-navbar :type="type">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          Henrique Gomide, Ph.D.
        </b-navbar-item>
      </template>
      <template slot="start">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          Home
        </b-navbar-item>
        <b-navbar-item tag="router-link" :to="{ path: '/resume' }">
          Resume
        </b-navbar-item>
        <b-navbar-item tag="router-link" :to="{ path: '/blog' }">
          Blog & Tutorials
        </b-navbar-item>
        <b-navbar-item tag="router-link" :to="{ path: '/research' }">
          Research
        </b-navbar-item>
      </template>

      <template slot="end">
        <b-navbar-item tag="div">
          <div id="social-network" class="buttons">
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
        </b-navbar-item>
      </template>
    </b-navbar>
    <br>
  </div>
</template>
<script>
export default {
  name: 'Headercomp',
  data () {
    return {
      type: 'is-dark'
    }
  }
}
</script>
