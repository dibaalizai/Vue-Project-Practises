<template>
  <div>{{ greet }}</div>
  {{ name }}
  <div v-html="channel"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>

  <h2 class="underline">Underlined Text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout? Movie</h2>
  <h2 v-bind:class="['new', 'promoted']">New Promoted Movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array Conditional Movie</h2>

  <h2 v-bind:class="{
    promoted: isPromoted, 
    new: isSoldout,
    'sold-out': isSoldout
    }">Object Conditional movie</h2>




</template>

<script>
export default {
  props: {},
  methods: {},
  name: "App",
  data() {
    return {
      greet: "Hello",
      name: "Diba",
      channel: "<b>Codevolution</b>",
      headingId: "heading",
      isDisabled: false,
      status: "danger",
      isPromoted: true,
      isSoldout: true,
    };
  },
};
</script>

<style scoped>
.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: green;
}

.sold-out {
  color: red;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
