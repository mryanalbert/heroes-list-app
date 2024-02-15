<script>
export default {
  // STATE
  data() {
    return {
      newHero: "",
      fname: "Ryan",
      lname: "Masungsong",
      heroes: [
        { name: "SuperGirl" },
        { name: "Flash" },
        { name: "Batman" },
        { name: "Arrow" },
        { name: "SuperMan" },
        { name: "SpiderMan" },
      ],
    };
  },
  // METHODS
  methods: {
    addHero() {
      if (this.newHero.trim() != "") {
        this.heroes.unshift({ name: this.newHero });
        this.newHero = "";
      }
    },
    randM() {
      return Math.random();
    },
    removeHero(name) {
      this.heroes = this.heroes.filter((hero) => hero.name != name);
    },
  },
  // COMPUTED PROPERTIES
  computed: {
    heroesCount() {
      return this.heroes.length;
    },
    randC() {
      return Math.random();
    },
    fullName() {
      return `${this.fname} ${this.lname}`;
    },
  },
};
</script>

<template>
  <div class="m-auto">
    <h1 class="text-2xl text-center">Dc Heroes {{ heroesCount }}</h1>

    <ul>
      <li class="flex justify-between" v-for="{ name } in heroes" :key="name">
        <div>{{ name }}</div>
        <button @click="removeHero(name)">x</button>
      </li>
    </ul>

    <form class="mt-10" @submit.prevent="addHero()">
      <input
        class="border rounded"
        v-model="newHero"
        placeholder="Type Hero Name Here"
      />
      <button
        class="border rounded bg-gradient-to-r from-red-700 to-pink-500 text-white"
      >
        Add Hero
      </button>
    </form>
    <small>Total Heroes in the list is {{ heroesCount }}</small>
  </div>
</template>

<style></style>
