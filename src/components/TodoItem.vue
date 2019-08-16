<template>
  <div>
  <li @click="handleDelete">{{ content }}</li>
  </div>
</template>

<script>
  export default {
    props: ["content", "index"],
    methods: {
      handleDelete: function() {
        this.$emit("delete", this.index);
      }
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
