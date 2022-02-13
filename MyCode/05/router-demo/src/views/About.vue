<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{id}}</p>
    <router-view></router-view>
  </div>
</template>
<script>
export default {
  props:['id'],
  setup() {},

  created() {
    console.log(this.$route);
  },
};
</script>