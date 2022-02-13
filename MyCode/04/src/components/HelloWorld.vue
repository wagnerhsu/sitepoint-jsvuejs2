<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" @input="updateMessage" :value="msg" />
    <h2>Result:</h2>
    {{ results }}
  </div>
</template>

<script>
import { ref, watch, onMounted } from "vue";
export default {
  name: "HelloWorld",
  setup() {
    const msg = ref("Hello");
    const results = ref("");
    watch(msg, () => {
      results.value = msg.value;
    });
    const updateMessage = (event) => (msg.value = event.target.value);
    onMounted(() => {
      console.log("onMounted...");
    });
    return {
      msg,
      results,
      updateMessage,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
