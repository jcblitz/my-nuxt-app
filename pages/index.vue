<template>
  <div>
    <section class="hero">
      <div class="hero-body">
        <div class="columns">
          <div class="column">
            <p class="title">My Collections</p>
            <p class="subtitle">A list of my stuff</p>
          </div>
          <div class="column level-item has-text-right">
            <b-button type="is-primary is-light" @click="clickMe"
              >New Collection</b-button
            >
          </div>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="columns is-desktop is-multiline">
        <div v-for="collection in collections" :key="collection.id" class="column is-3">
          <card
          :title="collection.name"
          icon="github">
          Open source on <a href="https://github.com/buefy/buefy"> GitHub </a>
        </card>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Card from '~/components/Card'


export default {
  name: 'IndexPage',
  components: {
    Card,
  },
  data() {
    return {
      posts: [],
      collections: [],
    }
  },
  async fetch() {
      this.collections = await fetch('https://amock.io/api/jcblitz/collections').then(res => res.json())
    },
  methods: {
    clickMe: () => {
      
    },
  },
}
</script>
