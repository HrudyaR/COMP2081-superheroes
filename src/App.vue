<template>
  <div id="app">
    <main class="mw6 center">
      <!-- <a
        class="f6 grow no-underline br-pill ba bw2 ph3 pv2 mb2 dib dark-blue"
        href="#0"
        @click="addHero"
        >Add Hero</a
      > -->
      <add-hero-button text="Add Hero" @add-hero="addHero"></add-hero-button>
      <twitter-short-profile
        v-for="hero in heroes"
        :key="hero.name"
        :superhero="hero"
      ></twitter-short-profile>
    </main>
  </div>
</template>

<script>
import TwitterShortProfile from "./components/TwitterShortProfile";
import AddHeroButton from "./components/AddHeroButton";
const heroes = [
  {
    name: "Prof. Xavier",
    twitter: "@profx",
    pic:
      "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0004.gif",
  },
  {
    name: "Spiderman",
    twitter: "@spidey",
    pic:
      "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0008.gif",
  },
  {
    name: "Wolverine",
    pic:
      "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0011.gif",
    twitter: "@logan",
  },
  {
    name: "Cyclops",
    twitter: "@oneye",
    pic:
      "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0005.gif",
  },
  {
    name: "Storm",
    twitter: "@rainsitpours",
    pic:
      "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0007.gif",
  },
  {
    name: "Phoenix",
    twitter: "@jeangrey",
    pic:
      "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0016.gif",
  },
];

export default {
  name: "App",
  components: {
    TwitterShortProfile,
    AddHeroButton,
  },
  data: function() {
    return {
      storage: heroes,
      heroes: [],
    };
  },
  methods: {
    addHero() {
      // if (this.storage.length) {
      //   this.heroes.push(this.storage.pop());
      // }
      this.storage.length > 0 && this.heroes.push(this.storage.pop());
    },
  },
};
</script>
