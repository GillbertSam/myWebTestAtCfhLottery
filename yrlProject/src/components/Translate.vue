<template>
  <div>
    <p>{{translateAnswer}}</p>
  </div>
</template>

<script>
export default {
  name: "Translate",
  props: ["translateAnswer"],
  data() {
    return {
      msg: "yrl"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
