<template>
  <div id="app">
    <section>
      <div class="text">
        <h1>Photo album</h1>
        <p>click on image to show it up</p>
      </div>
      <div class="b-container">
        <div v-for="image in images" class="image">
          <img v-b-tooltip.hover :title="image.text" v-b-modal.modal1 :src="image.url" :alt="image.text" @click="activeImageUrl = image.url; activeImageText = image.text" >
        </div>
        <b-modal :hide-footer="true" id="modal1" :title="activeImageText">
          <img class="modal-img" :src="activeImageUrl" :alt="activeImageText">
        </b-modal>
      </div>
      <div class="end"></div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      images: [
          {url: require('./assets/logo.png'), text: 'Vue'},
          {url: require('./assets/google.png'), text: 'Google'},
          {url: require('./assets/facebook.png'), text: 'Facebook'},
          {url: require('./assets/twitter.png'), text: 'Twitter'},
          {url: require('./assets/microsoft.png'), text: 'Microsoft'},
          {url: require('./assets/amazon.png'), text: 'Amazon'},
          {url: require('./assets/pepsi.png'), text: 'Pepsi'},
          {url: require('./assets/cocacola.png'), text: 'Coca cola'},
          {url: require('./assets/react.png'), text: 'React'},
          {url: require('./assets/angular.png'), text: 'Angular'},
          {url: require('./assets/nasa.png'), text: 'Nasa'},
          {url: require('./assets/pringles.png'), text: 'Pringles'},
          {url: require('./assets/lays.png'), text: 'Lays'},
          {url: require('./assets/mcdonalds.png'), text: 'McDonalds'},
          {url: require('./assets/twitch.png'), text: 'Twitch'},
          {url: require('./assets/adidas.png'), text: 'Adidas'},
          {url: require('./assets/7up.png'), text: '7up'},
          {url: require('./assets/apple.png'), text: 'Apple'},
          {url: require('./assets/nvidia.png'), text: 'Nvidia'},
          {url: require('./assets/instagram.png'), text: 'Instagram'},
          {url: require('./assets/snapchat.png'), text: 'Snapchat'},
          {url: require('./assets/zalando.png'), text: 'Zalando'},
          {url: require('./assets/skype.png'), text: 'Skype'},
          {url: require('./assets/chupachups.png'), text: 'Chupa Chups'},
          {url: require('./assets/starbucks.png'), text: 'Starbucks'},
          {url: require('./assets/pinterest.png'), text: 'Pinterest'},
          {url: require('./assets/pizzahut.png'), text: 'Pizza Hut'},
          {url: require('./assets/total.png'), text: 'Total' },
          {url: require('./assets/fanta.png'), text: 'Fanta'},
          {url: require('./assets/sprite.png'), text: 'Sprite'},
          {url: require('./assets/kfc.png'), text: 'KFC'},
          {url: require('./assets/intel.png'), text: 'Intel'},
      ],
        activeImageUrl: null,
        activeImageText: null,
    }
  }
}
</script>

<style lang="scss">

  body {
    background-color: #e6e6e8;
    color: #300032;
    font-family: 'Roboto Slab', serif;
  }

  section {
    width: 100%;
    height: auto;
    text-align: center;
    .text {
      width: 100%;
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      margin-bottom: 100px;
      margin-top: 100px;
      h1 {
        font-size: 80px;
        letter-spacing: .15em;
      }
    }
    div {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -ms-flex-wrap: wrap;
      flex-wrap: wrap;
      -webkit-box-pack: center;
      -ms-flex-pack: center;
      justify-content: center;
      .image {
        height: 200px;
        width: 300px;
        margin: 10px;
        padding: 10px;
        -webkit-box-shadow: 20px 25px 25px 0 rgba(0,0,0,.2);
        box-shadow: 20px 25px 25px 0 rgba(0,0,0,.2);
        -webkit-transition: -webkit-box-shadow 2s;
        transition: -webkit-box-shadow 2s;
        -o-transition: box-shadow 2s;
        transition: box-shadow 2s, -webkit-box-shadow 2s;
        &:hover {
          -webkit-box-shadow: none;
          box-shadow: none;
        }
        img {
          max-width: 100%;
          max-height: 100%;
          -webkit-animation-name: gray;
          animation-name: gray;
          -webkit-animation-duration: 3s;
          animation-duration: 3s;
          cursor: pointer;
          @-webkit-keyframes gray {
            0%   {-webkit-filter: grayscale(100%);filter: grayscale(100%);}
            10%   {-webkit-filter: grayscale(90%);filter: grayscale(90%);}
            20%   {-webkit-filter: grayscale(80%);filter: grayscale(80%);}
            30%  {-webkit-filter: grayscale(70%);filter: grayscale(70%);}
            40%  {-webkit-filter: grayscale(60%);filter: grayscale(60%);}
            50%  {-webkit-filter: grayscale(50%);filter: grayscale(50%);}
            60%  {-webkit-filter: grayscale(40%);filter: grayscale(40%);}
            70%  {-webkit-filter: grayscale(30%);filter: grayscale(30%);}
            80%  {-webkit-filter: grayscale(20%);filter: grayscale(20%);}
            90%  {-webkit-filter: grayscale(10%);filter: grayscale(10%);}
            100%  {-webkit-filter: grayscale(0%);filter: grayscale(0%);}
          }
          @keyframes gray {
            0%   {-webkit-filter: grayscale(100%);filter: grayscale(100%);}
            10%   {-webkit-filter: grayscale(90%);filter: grayscale(90%);}
            20%   {-webkit-filter: grayscale(80%);filter: grayscale(80%);}
            30%  {-webkit-filter: grayscale(70%);filter: grayscale(70%);}
            40%  {-webkit-filter: grayscale(60%);filter: grayscale(60%);}
            50%  {-webkit-filter: grayscale(50%);filter: grayscale(50%);}
            60%  {-webkit-filter: grayscale(40%);filter: grayscale(40%);}
            70%  {-webkit-filter: grayscale(30%);filter: grayscale(30%);}
            80%  {-webkit-filter: grayscale(20%);filter: grayscale(20%);}
            90%  {-webkit-filter: grayscale(10%);filter: grayscale(10%);}
            100%  {-webkit-filter: grayscale(0%);filter: grayscale(0%);}
          }
        }
      }
      .modal-img {
        height: 300px;
        width: auto;
      }
    }
    .end {
      height: 100px;
    }
  }

</style>
