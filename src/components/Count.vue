<template>
  <div>
    <a @click="handleOnClickCountUp">{{count}} clicked!! </a>
  </div>
</template>
<script>
import store from '../store'
export default {
  name: 'count',
  components: {},
  data: () => store.state,
  methods: {
    handleOnClickCountUp: function(e) {
      e.preventDefault();
      this.count++;
    }
  }
}
</script>
<style>
</style>
