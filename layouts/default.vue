<template>
  <div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>
<script>
import Header from '~/components/Header'
import Footer from '~/components/Footer'

export default {
  components: {
    Header,
    Footer
  }
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Fira+Code&family=IBM+Plex+Sans&display=swap');
@import "~bulma/sass/utilities/_all";

$primary: #d79921;
$primary-invert: findColorInvert($primary);
$twitter: #cc241d;
$twitter-invert: findColorInvert($twitter);
$info: #98971a;
$dark: #282828;
$light: #fbf1c7;
$success: #458588;
$warning: #d65d0e;
$danger: #cc241d;

// Setup $colors to use as bulma classes (e.g. 'is-twitter')
$colors: (
  "white": (
    $white,
    $black
  ),
  "black": (
    $black,
    $white
  ),
  "light": (
    $light,
    $light-invert
  ),
  "dark": (
    $dark,
    $dark-invert
  ),
  "primary": (
    $primary,
    $primary-invert
  ),
  "info": (
    $info,
    $info-invert
  ),
  "success": (
    $success,
    $success-invert
  ),
  "warning": (
    $warning,
    $warning-invert
  ),
  "danger": (
    $danger,
    $danger-invert
  ),
  "twitter": (
    $twitter,
    $twitter-invert
  )
);

// Links
$link: $primary;
$link-invert: $primary-invert;
$link-focus-border: $primary;

// Import Bulma and Buefy styles
@import "~bulma";
@import "~buefy/src/scss/buefy";

#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav,
h1 {
  font-family: "Fira Code", monospace;
  font-weight: 600;
}

h2,
h3,
h4,
h5,
p {
  font-family: "IBM Plex Sans", sans-serif;
}

iframe {
    padding: 50px 0;
}

</style>
