<template>
  <div>
    <h3>Mi nombre</h3>
    <pre><code>{{user}}</code></pre>
    <button v-if="!user.addr" @click="$fcl.authenticate">login</button>
    <button v-else @click="$fcl.unauthenticate">logout</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      user: {},
    };
  },
  mounted() {
    this.$fcl.currentUser().subscribe((user) => (this.user = user));
  },
};
</script>