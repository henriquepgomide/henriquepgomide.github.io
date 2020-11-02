<template>
  <footer class="footercomp">
    <div class="container">
      <div class="columns">
        <div id="hpg" class="column">
          <div class="columns">
            <div class="column is-one-third">
              <figure class="image is-128x128">
                <img
                  class="is-rounded"
                  src="~assets/imgs/henrique-gomide.jpg"
                >
              </figure>
            </div>
            <div class="column">
              <h2 class="title">
                Henrique Gomide
              </h2>
              <h2 class="subtitle">
                TensorFlow Developer
              </h2>
              <div id="social-network" class="columns">
                <div class="column">
                  <figure class="image is-32x32">
                    <img src="https://api.accredible.com/v1/frontend/credential_website_embed_image/badge/24952440" alt="TensorFlow Developer Certificate">
                  </figure>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="column" />
        <div class="column is-one-fourth">
          <figure class="image is-256x256">
            <a
              href="https://buttercms.com"
            ><img src="~assets/imgs/butter-y.png">
            </a>
          </figure>
        </div>
      </div>
    </div>
  </footer>
</template>
<style scoped>
.footercomp {
  margin-top: 10rem;
}

#hpg {
  padding-top: 2rem;
}

.logo {
  width: 50px;
}

.logo:hover {
  filter: invert(53%) sepia(69%) saturate(5720%) hue-rotate(340deg)
    brightness(102%) contrast(105%);
}
</style>
