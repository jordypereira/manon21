<template>
  <div class="hello">
    <img
      v-bind:src="giveKittyImage()"
      alt="Kitty"
      class="kitty animated"
      v-for="kitty in kitties"
      v-bind:class="giveClass()"
      :key="kitty"
    >
    <div class="text">
      <h1>{{ msg }}</h1>
      <h2>Redenen waarom je zo fantastisch bent:</h2>
      <ul>
        <li>je bent
          <b>SUPER</b> knap.
        </li>
        <li>Altijd opgewekt en kan op iedereen zijn gezicht een glimlach toveren.</li>
        <li>Ik heb dit letterlijk een half uur voor 12 gemaakt en het zou jammer zijn als het pas volgend jaar af zou zijn maar je bent gewoonweg de beste</li>
      </ul>
    </div>
    <img
      src="https://media.giphy.com/media/lzkwynp2MTLeo/giphy.gif"
      alt="fireworks"
      class="fireworks"
    >
    <img src="./../assets/manon.jpg" id="manon">
    <img
      src="https://media.giphy.com/media/lzkwynp2MTLeo/giphy.gif"
      alt="fireworks"
      class="fireworks"
    >
    <img src="https://media.giphy.com/media/peAFQfg7Ol6IE/giphy.gif" alt="Fireworks" class="f-left">
    
    <button v-on:click="spawnKitty()">Doneer een katje aan Manon</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'PROFICIAT MET JE 21STE VERJAARDAG!',
      kitties: 0,
      classes: [
        'bounceInDown',
        'bounceInLeft',
        'bounceInRight',
        'bounceInUp',
        'swing',
        'wobble',
        'rubberBand',
        'jello',
      ],
      kittyImg: [
        'https://cdn.shopify.com/s/files/1/1369/6411/files/cutest-cat-gifs-kitten-meow_large.gif?v=1504275637',
        'https://media1.tenor.com/images/944b4dda3cc83af427dabfa49a635af3/tenor.gif?itemid=5551196',
        'https://media1.tenor.com/images/f6fe8d1d0463f4e51b6367bbecf56a3e/tenor.gif?itemid=7245759',
        'https://78.media.tumblr.com/f5dab5e78e8db150a6c5d9d7c7a0281f/tumblr_p1dcqvcsN41qm4dj5o1_400.gif',
        'https://i.imgur.com/PXFPVEG.gif',
        'https://media1.tenor.com/images/1c723b0ebef6eacbc0807e35a326b9c3/tenor.gif?itemid=7660902',
        'https://cdn.shopify.com/s/files/1/1369/6411/files/cutest-cat-gifs-kitten-heads_large.gif?v=1504275657',
        'http://www.pbh2.com/wordpress/wp-content/uploads/2013/03/cutest-kitten-gifs-massage.gif',
        'https://i.pinimg.com/originals/61/08/2b/61082b41002898b4be5478b7a347a3af.gif',
      ],
    }
  },
  methods: {
    spawnKitty() {
      this.kitties++
      window.scrollTo(0, 0)
    },
    giveClass() {
      return this.classes[Math.floor(Math.random() * this.classes.length)]
    },
    giveKittyImage() {
      return this.kittyImg[Math.floor(Math.random() * this.kittyImg.length)]
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
}
.f-left {
  width: 250px;
  height: auto;
}
.fireworks {
  width: 200px;
  height: 100px;
}
.kitty {
  width: 400px;
  height: auto;
}
#manon {
  width: 500px;
  height: 500px;
}
button {
  position: fixed;
  left: 50%;
  top: 50%;
  background-color: pink;
  padding: 20px 50px;
  transition: 2s all;
  border: none;
  border-radius: 4px;
}
button:hover {
  background-color: lightskyblue;
  cursor: pointer;
}
</style>
