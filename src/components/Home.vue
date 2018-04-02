<template>
  <div class="home">
    <div class="container">
      <div class="section-1 row">
        <div class="col-md-6 d-flex align-items-center justify-content-center">
          <div class="d-flex flex-row h-100 w-100">
            <img class="home-banner" src="../assets/images/assessment.jpg">
            <a v-on:click="openTheModal" class="video-player-icon"><img src="../assets/images/video-play-icon.png"></a>
            <bootstrap-modal ref="theModal" :size="'large'" :need-header="false" :need-footer="false" :closed="pauseVideo">
              <div slot="body">
                  <iframe id="videoPlayer" src="//www.youtube.com/embed/YE7VzlLtp-4" width="800" height="500" frameborder="0" allowfullscreen></iframe>
              </div>
            </bootstrap-modal>
          </div>
        </div>
        <div class="col-md-6 d-flex align-items-center justify-content-center flex-column position-relative">
          <h1 class="font-weight-bold">Assess through gaming</h1>
          <h3>This Company</h3>
          <div class="row mt-5">
            <button class="btn btn-primary">How we can help you</button>
            <button class="btn btn-default ml-3">Free guide</button>
          </div>
          <div class="more">
            <i class="fa fa-long-arrow-down"></i>
          </div>
        </div>
      </div>
    </div>
    <div class="message">
      <a><img src="../assets/images/messages-icon.png"></a>
    </div>
  </div>
</template>

<script>export default {
  name: 'Home',
  components: {
    'bootstrap-modal': require('vue2-bootstrap-modal')
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    openTheModal () {
      this.$refs.theModal.open()
    },
    pauseVideo () {
      var frame = document.getElementById('videoPlayer')
      frame.contentWindow.postMessage('{"event":"command","func":"pauseVideo","args":""}', '*')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.section-1 {
  height: calc(100vh - 88px);

  h1 {
    font-size: 60px;
  }
}

img.home-banner {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.message {
  width: 50px;
  height: 50px;
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 9999;
  cursor: pointer;

  img {
    width: 100%;
    height: 100%;
  }
}

.more {
  position: absolute;
  width: 30px;
  left: 30px;
  bottom: 10px;
  font-size: 30px;
  cursor: pointer;
  -webkit-transition: 0.5s ease-in-out;
  -moz-transition: 0.5s ease-in-out;
  -o-transition: 0.5s ease-in-out;
  transition: 0.5s ease-in-out;

  &:hover {
    left: 30px;
    bottom: 0;
  }
}

.video-player-icon {
  width: 50px;
  height: 50px;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  margin: auto;
  cursor: pointer;

  img {
    width: 100%;
    height: 100%;
  }

  &:hover {
    width: 55px;
    height: 55px;
  }
}
</style>
