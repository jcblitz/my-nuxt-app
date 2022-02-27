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
      <div class="columns is-mobile">
        <card
          v-for="collection in collections"
          :key="collection.name"
          :title="collection.name"
          icon="github"
        >
          Open source on <a href="https://github.com/buefy/buefy"> GitHub </a>
        </card>
      </div>
    </section>

    <section class="section">
      <div class="columns is-mobile">
        <card title="Guitars" icon="github">
          Open source on <a href="https://github.com/buefy/buefy"> GitHub </a>
        </card>

        <card title="Responsive" icon="cellphone-link">
          <b class="has-text-grey"> Every </b> component is responsive
        </card>

        <card title="Modern" icon="alert-decagram">
          Built with <a href="https://vuejs.org/"> Vue.js </a> and
          <a href="http://bulma.io/"> Bulma </a>
        </card>

        <card title="Lightweight" icon="arrange-bring-to-front">
          No other internal dependency
        </card>
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
      collections: [
        {
          title: 'Guitars',
          icon: null,
          name: 'Guitars',
          shortDescription: 'Nothing fancy, but I like them',
        },
        {
          title: 'Funko Pops',
          icon: null,
          name: 'Funko',
          shortDescription: 'My bobble heads, mostly Funko',
        },
        {
          title: 'Halloween Skeletons',
          icon: null,
          name: 'Halloween Skeletons',
          shortDescription: 'Nothing fancy, but I like them',
        },
        {
          title: 'Workshop Tools',
          icon: null,
          name: 'Tools',
          shortDescription: 'My bobble heads, mostly Funko',
        },
      ],
    }
  },
  methods: {
    clickMe: () => {
      // no op
    },
  },
}
</script>
