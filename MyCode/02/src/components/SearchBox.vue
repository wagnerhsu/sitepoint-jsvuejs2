<template>
  <div class="searchbox">
    <label>Terms<input v-model="terms" /></label>
    <button @click="$emit('search', terms)">Search</button>
  </div>
</template>

<script>
export default {
    name: 'SearchBox',
    data() {
        return {
            terms: ''
        }
    }
}
</script>