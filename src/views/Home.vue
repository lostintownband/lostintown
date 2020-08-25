/* eslint-disable max-len */
<template>
  <div class="home">
    <div v-if="!webSite">
      <!-- h1>Lost in Town</h1 -->
      <div class="back-img">
        <b-img :src="require('../assets/lost in town font.jpg')"></b-img>
      </div>
      <div class="container-mobile">
        <div class="spotify-song">
          <div class="songbox">
            <iframe
              src="https://open.spotify.com/embed/playlist/0raizyE8fEOPOwgWtYS9Wq"
              width="300"
              height="80"
              frameborder="0"
              allowtransparency="true"
              allow="encrypted-media"
            />
          </div>
        </div>
        <div class="btn-link">
          <div class="partOne">
            <p>
              <span>
                <font-awesome-icon :icon="['fab', 'youtube']" />
              </span>
              YouTube
            </p>
            <p>
              <span>
                <font-awesome-icon :icon="['fab', 'facebook-square']" />
              </span>
              Facebook
            </p>
            <p>
              <span>
                <font-awesome-icon :icon="['fab', 'spotify']" />
              </span>
              Spotify
            </p>
          </div>
          <div class="partTwo">
            <p>
              <span>
                <font-awesome-icon :icon="['fab', 'instagram']" />
              </span>
              Instagram
            </p>
            <p>
              <span>
                <font-awesome-icon :icon="['fab', 'apple']" />
              </span>
              Apple Music
            </p>
            <p>
              <span>
                <font-awesome-icon :icon="['fab', 'apple']" />
              </span>
              Space-X
            </p>
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

<script src="https://sdk.scdn.co/spotify-player.js"></script>
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
  .back-img {
    position: relative;
    z-index: 1;
  }
  img {
    width: 90%;
    margin-bottom: 50px;
    margin-top: -155px;
  }
  .container-mobile {
    position: relative;
    z-index: 1;
    margin-top: -135px;
    background-color: black;
    padding-top: 10px;
    .spotify-song {
      margin: 20px 10px;
    }
  }
  p {
    color: white;
    border: 1px solid;
    border-radius: 25px;
    span {
      margin-right: 10px;
    }
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
  .btn-link {
    display: flex;
    justify-content: space-evenly;
    /* p {
      text-align: right;
      padding-right: 10px;
    } */
    span {
      float: left;
      margin-left: 15px;
    }
    .partOne {
      width: 42%;
    }
    .partTwo {
      width: 42%;
    }
  }
}
</style>
