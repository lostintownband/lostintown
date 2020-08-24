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
            <b-img
              :src="require('../assets/lost in town font.jpg')"
              style="width: 30%;"
            ></b-img>
            <audio
              controls
              src="../assets/ELVIS MASTER 44.1 16BITS GOOD .wav">
                Your browser does not support the
                <code>audio</code> element.
            </audio>
          </div>
        </div>
        <div class="btn-link">
          <div class="partOneLink">
            <b-row>
              <b-col
                class="icon-link"
                @click="linkYoutube"
              >
                <!-- b-img :src="require('../assets/youtube.png')"></b-img -->
                <p>
                  <span>
                    <font-awesome-icon :icon="['fab', 'youtube']" />
                  </span>
                  YouTube
                </p>
              </b-col>
              <b-col
                class="icon-link"
                @click="linkFacebook"
              >
                <!-- b-img :src="require('../assets/facebook.png')"></b-img -->
                <p>
                  <span>
                    <font-awesome-icon :icon="['fab', 'facebook-square']" />
                  </span>
                  Facebook
                </p>
              </b-col>
            </b-row>
            <b-row>
              <b-col
                class="icon-link"
                @click="linkSpotify"
              >
                <!-- b-img :src="require('../assets/spotify.png')"></b-img -->
                <p>
                  <span>
                    <font-awesome-icon :icon="['fab', 'spotify']" />
                  </span>
                  Spotify
                </p>
              </b-col>
              <b-col
                class="icon-link"
                @click="linkInstagram"
              >
                <!-- b-img :src="require('../assets/instagram.png')"></b-img -->
                <p>
                  <span>
                    <font-awesome-icon :icon="['fab', 'instagram']" />
                  </span>
                  Instagram
                </p>
              </b-col>
            </b-row>
            <b-row>
              <b-col
                class="icon-link"
                @click="linkApple"
              >
                <!-- b-img :src="require('../assets/apple.png')"></b-img -->
                <p>
                  <span>
                    <font-awesome-icon :icon="['fab', 'apple']" />
                  </span>
                  Apple Music
                </p>
              </b-col>
              <b-col
                class="icon-link"
                @click="linkApple"
              >
                <!-- b-img :src="require('../assets/apple.png')"></b-img -->
                <p>
                  <span>
                    <font-awesome-icon :icon="['fab', 'apple']" />
                  </span>
                  Space-X
                </p>
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

<script src="https://sdk.scdn.co/spotify-player.js"></script>
<script>
export default {
  data: () => ({
    webSite: false,
    youTube: '',
  }),
  mounted() {
    this.test();
  },
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
    test() {
      window.onSpotifyWebPlaybackSDKReady = () => {
        const partOne = 'BQDW8Y1jf5gN1VlRpnEtqdLLhGVd-z-lCKphrWCy0o2VQxUHfoURmX';
        const partTwo = 'sJgDybt8LtDXblOjlvadOuYajMEZFxuiSJfKvrrE49X-aQR338JVLl';
        const partThree = 'cD1VqooEYerMT8-FmltdIE57xzEX8SMr4rcTNN-uH97LrSBw1pD';
        const partFour = 'P3EtOOKWaRc_-2UmTtxtDVj0';
        const token = `${partOne}${partTwo}${partThree}${partFour}`;
        console.log(token);
        const player = new Spotify.Player({
          name: 'Web Playback SDK Quick Start Player',
          getOAuthToken: (cb) => { cb(token); },
        });
        // Error handling
        player.addListener('initialization_error', ({ message }) => { console.error(message); });
        player.addListener('authentication_error', ({ message }) => { console.error(message); });
        player.addListener('account_error', ({ message }) => { console.error(message); });
        player.addListener('playback_error', ({ message }) => { console.error(message); });
        // Playback status updates
        player.addListener('player_state_changed', (state) => { console.log(state); });
        // Ready
        player.addListener('ready', ({ deviceId }) => {
          console.log('Ready with Device ID', deviceId);
        });
        // Not Ready
        player.addListener('not_ready', ({ deviceId }) => {
          console.log('Device ID has gone offline', deviceId);
        });
        // Connect to the player!
        player.connect();
      };
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
    margin-bottom: 30px;
    margin-top: -180px;
  }
  .container-mobile {
    position: relative;
    z-index: 1;
    margin-top: -135px;
    background-color: black;
    padding-top: 30px;
    .spotify-song {
      margin-top: 150px;
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
}
</style>
