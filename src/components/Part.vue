<template>
  <a :href="link" target="_blank">
    <div class="part">
      <h2>{{ name }}</h2>
      <p>{{ desc }}</p>

      <p>{{ category }}</p>
    </div>
  </a>
</template>

<script>
export default {
  name: 'Part',
  props: {
    name: String,
    desc: String,
    link: String,
    category: String,
    auth: {
      type: Boolean,
      default: false,
      required: false,
    },
    https: {
      type: Boolean,
      default: false,
      required: false,
    },
    cors: {
      type: Boolean,
      default: false,
      required: false,
    },
  },
};
</script>

<style scoped>
a {
  font-size: 1.3rem;
  text-decoration: none;
  color: black;
}
.part {
  border-radius: 5px;
  margin: 20px;
  padding: 12px;

  height: 80%;

  box-shadow: -6px 6px 0 black;

  background: #ffa630;
}

.part:hover {
  background: #edc775;
}
</style>
