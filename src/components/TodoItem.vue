<template>
  <li @click="handleClick">{{content}}</li>
</template>

<script>
export default {
  props: ['content', 'index'],
  methods: {
    handleClick: function () {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  color: #666;
}
</style>
