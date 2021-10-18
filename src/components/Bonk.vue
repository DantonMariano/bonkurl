<template>
  <div class="bonk">
    <div class="decor"></div>
    <div class="title">
      <h3>Bonk your URL! 🐶🏏</h3>
    </div>
    <div class="content">
      <div class="url-output">
        <input type="text" v-model="url" disabled />
        <button @click="shortenUrl">
          <span> {{ btnState }}</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Bonk",

  data() {
    return {
      url: "",
      btnState: "Bonk!",
      currentUrl: "",
    };
  },
  methods: {
    shortenUrl() {
      if (this.url) {
        navigator.clipboard.writeText(this.url).then(
          function() {},
          function(err) {
            console.error(err);
          }
        );
        this.btnState = "Copy!";
      } else {
        axios
          .post("http://www.tuqurl.xyz/short/insert", {
            urltoshort: this.currentUrl,
          })
          .then((res) => {
            this.url = `tuqurl.xyz/${res.data.url}`;
          });
      }
    },
  },
  mounted() {
    chrome.tabs.query({ active: true, currentWindow: true }).then((tab) => {
      this.currentUrl = tab[0].url;
    });
  },
};
</script>

<style lang="scss">
.bonk {
  display: flex;
  flex-direction: column;
}

.decor {
  height: 1rem;
  width: 100%;
  display: flex;
  padding: -3rem;
  background: #ce5542;
}

.title {
  text-align: start;
  margin: 0 1rem;
}
.content {
  margin: 2rem 1rem;
  .url-output {
    display: flex;
    flex-direction: row;
    position: relative;

    input {
      min-height: 1.6rem;
      flex-grow: 2;
      padding: 0.2rem 1rem;
      border: none;
      border-radius: 15px;
      box-shadow: 0 2px 3px 1px rgba(0, 0, 0, 0.2);
      &:focus {
        outline: none;
      }
    }

    button {
      position: absolute;
      right: 0;
      width: auto;
      padding: 1rem;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 1.65rem;
      cursor: pointer;
      outline: none;
      border: none;
      border-radius: 0px 15px 15px 0;
      font-family: "Patrick Hand", cursive;
      background: #cebaab;
      font-size: 1rem;

      color: #555554, #ce5542, #efdcac, #cebaab, #ab8777, #555554, #ce5542,
        #efdcac;
      span {
        text-transform: uppercase;
        font-weight: bold;
      }
    }
  }
}
</style>
