<template>
  <div>
    <a @click="handleOnClickCountUp">{{count}} clicked!! </a>
  </div>
</template>
<script>
export default {
  name: 'count',
  components: {},
  props: ['count'],
  methods: {
    handleOnClickCountUp: function(e) {
      e.preventDefault()
      this.$emit('count-up')
    }
  }
}
</script>
<style>
</style>
