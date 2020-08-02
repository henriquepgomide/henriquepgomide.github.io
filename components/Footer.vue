<template>
  <footer class="footercomp">
    <div class="container">
      <div class="columns">
        <div id="hpg" class="column">
          <div class="columns">
            <div class="column is-one-third">
              <figure class="image is-64x64">
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
                Assistant professor @UFV
              </h2>

              <div id="social-network" class="columns">
                <div class="column">
                  <a
                    href="https://github.com/henriquepgomide"
                  ><img
                    class="is-rounded logo"
                    src="~assets/icons/github.svg"
                  ></a>
                  <a
                    href="https://www.linkedin.com/in/hpgomide/"
                  >
                    <img
                      class="is-rounded logo"
                      src="~assets/icons/linkedin.svg"
                    ></a>
                  <a
                    href="https://www.youtube.com/c/HenriqueGomide/"
                  ><img class="is-rounded logo" src="~assets/icons/youtube.svg">
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="column" />
        <div class="column">
          <figure class="image">
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
