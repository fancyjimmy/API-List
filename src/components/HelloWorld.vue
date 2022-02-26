<template>
  <div class="elem">
    <Part
      v-for="entry in entries"
      :name="entry.API"
      :desc="entry.Description"
      :link="entry.Link"
      :category="entry.Category"
    />
  </div>
</template>

<script>
import Part from './Part.vue';

export default {
  name: 'HelloWorld',
  components: { Part },
  data() {
    return {
      entries: [],
    };
  },
  methods: {
    getData() {
      fetch('https://api.publicapis.org/entries')
        .then((res) => res.json())
        .then((res) => {
          this.entries = res.entries;
        });
    },
  },
  created() {
    fetch('https://api.publicapis.org/entries', {
      'Access-Control-Allow-Origin': 'https://api.publicapis.org/entries',
    })
      .then((res) => res.json())
      .then((res) => {
        this.entries = res.entries;
      });
  },
};
</script>

<style scoped>
.elem {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}
</style>
