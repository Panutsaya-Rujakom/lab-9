<template>
  <div>
    <div class="container">
      <br />
      <br />
      <br />
      <b-avatar
        id="ss"
        src="https://c.pxhere.com/photos/e3/d1/headsets_music_pink_background_player_beautiful_to_listen_emotions-1283476.jpg!d"
        size="15%"
      ></b-avatar>
      <br /><br />
      <b-row id="cc">
        <b-col cols="5">
          <div>
            <b-card id="sss">
              <template v-slot:header>
                <h1 id="te" class="mb-0">The Music</h1>
              </template>

              <b-card-body id="sss">
                <input id="sd" v-model="textSearch" type="text" placeholder="Search" />
                <button id="sss" @click="searchData()">Search</button>
              </b-card-body>
            </b-card>
          </div>
        </b-col>
        <b-col cols="8">
          <div v-for="list in playList" :key="list.trackId" class="mt-4">
            <b-card
              no-body
              class="overflow-hidden"
              style="width: 100%"
              border-variant="info"
            >
              <b-row no-gutters>
                <b-col md="2">
                  <b-card-img
                    :src="list.artworkUrl100"
                    :alt="list.artistName"
                    class="rounded-0"
                  />
                  <router-link
                    :to="{
                      name: 'MureInfo',
                      params: {
                        TrackName: list.trackName,
                        ArtistName: list.artistName,
                        CollectionName: list.collectionName,
                        TrackNumber: list.trackNumber,
                        ReleaseDate: list.releaseDate,
                        TrackCount: list.trackCount,
                        CollectionPrice: list.collectionPrice,
                        Currency: list.currency,
                        TrackPrice: list.trackPrice,
                        CollectionViewUrl: list.collectionViewUrl,
                        ArtworkUrl100: list.artworkUrl100,
                        PreviewUrl: list.previewUrl,
                        ArtistViewUrl: list.artistViewUrl,
                      },
                    }"
                  >
                    <b-button variant="info">   ___Detail___  </b-button>
                  </router-link>
                </b-col>
                <b-col id="ta" md="10">
                  <b-card-body :title="list.trackName">
                    <div>Artist : {{ list.artistName }}</div>
                    <div>Collection : {{ list.collectionName }}</div>
                    <b-card-text>
                      <audio controls>
                        <source :src="list.previewUrl" type="audio/mpeg" />
                      </audio>
                    </b-card-text>
                  </b-card-body>
                </b-col>
              </b-row>
            </b-card>
          </div>
        </b-col>
      </b-row>
      <br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      playList: null,
      textSearch: "",
    };
  },

  methods: {
    searchData() {
      axios
        .get(
          "https://itunes.apple.com/search?term=+" +
            this.textSearch +
            "&limit=100"
        )
        .then((response) => {
          this.playList = response.data.results.slice(1, 15);
        })
        .catch((err) => {
          // eslint-disable-next-line no-console
          console.log(err);
        });
    },
  },
};
</script>

<style>
#text {
  font-size: 20px;
  color: rgb(0, 0, 0);
}
#te {
  font-size: 40px;
  text-align: center;
}
#ta {
  text-align: center;
}
#cc {
  display: flex;
  justify-content: center;
  margin-left: 50px;
}
#ss {
  display: flex;
  justify-content: center;
  margin-left: 500px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
#sss{
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  background-color: rgb(248, 220, 233);
  border-radius: 15px;
}
#sd{
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
</style>
