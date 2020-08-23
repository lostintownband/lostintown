<template>
  <div class="home">
    <div v-if="!webSite">
      <h1>Lost in Town</h1>
      <div class="spotify-song">
        <b-img :src="require('../assets/lost in town font.jpg')"></b-img>
        <div class="songbox">
          <audio
            controls
            src="../assets/ELVIS MASTER 44.1 16BITS GOOD .wav">
              Your browser does not support the
              <code>audio</code> element.
          </audio>
        </div>
      </div>
      <div class="container-mobile">
        <div class="btn-link">
          <div class="partOneLink">
            <b-row>
              <b-col
                class="icon-link"
                @click="linkYoutube"
              >
                <b-img :src="require('../assets/youtube.png')"></b-img>
                <p>YouTube</p>
              </b-col>
              <b-col
                class="icon-link"
                @click="linkFacebook"
              >
                <b-img :src="require('../assets/facebook.png')"></b-img>
                <p>Facebook</p>
              </b-col>
            </b-row>
            <b-row>
              <b-col
                class="icon-link"
                @click="linkSpotify"
              >
                <b-img :src="require('../assets/spotify.png')"></b-img>
                <p>Spotify</p>
              </b-col>
              <b-col
                class="icon-link"
                @click="linkInstagram"
              >
                <b-img :src="require('../assets/instagram.png')"></b-img>
                <p>Instagram</p>
              </b-col>
            </b-row>
            <b-row>
              <b-col
                class="icon-link"
                @click="linkApple"
              >
                <b-img :src="require('../assets/apple.png')"></b-img>
                <p>Apple Music</p>
              </b-col>
              <b-col
                class="icon-link"
                @click="linkApple"
              >
                <b-img :src="require('../assets/apple.png')"></b-img>
                <p>Space-X</p>
              </b-col>
            </b-row>
          </div>
        </div>
        <div class="site-link">
          <b-button @click="showWork">Visite Ours WebSite ?</b-button>
        </div>
      </div>
    </div>
    <div v-else>
      <h1>Working Progress !!</h1>
      <div class="site-link">
        <b-button @click="showWork">Go Back To All Links ?</b-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    webSite: false,
    youTube: '',
  }),
  methods: {
    linkYoutube() {
      window.open('https://www.youtube.com/channel/UCZ7JcnkKEDBxr9FsJqX7S-A');
    },
    linkFacebook() {
      window.open('https://www.facebook.com/lostintownband/');
    },
    linkSpotify() {
      window.open('https://open.spotify.com/artist/3QkqNxsY6EhNAZyk5qB7gk');
    },
    linkInstagram() {
      window.open('https://www.instagram.com/lostintown_band/');
    },
    linkApple() {
      window.open('https://music.apple.com/gb/artist/lost-in-town/1514968132');
    },
    showWork() {
      this.webSite = !this.webSite;
    },
  },
};
</script>

<style lang="scss">
.home {
  padding-top: 30px;
  padding-bottom: 30px;
  line-height: 30px;
  .songbox {
    audio {
      width: 80%;
      height: 25px;
      border-radius: 10px;
      margin: 10px 10px;
    }
  }
  .row {
    margin: 0;
  }
  img {
    width: 30%;
  }
  p {
    color: white;
  }
  button {
    background-color: transparent;
    height: 25px;
    width: 100%;
    padding: 0;
    border: none;
  }
  .site-link {
    margin: 20px 10px;
    button {
      width: 50%;
      border: 1px solid black;
    }
  }
  .icon-link {
    cursor: pointer;
  }
  h1 {
    color: white;
    margin-bottom: 25px;
  }
}
</style>
