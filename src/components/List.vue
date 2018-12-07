<template>
  <div>
    <h3>{{title}}</h3>
    <ul class="list">
      <li v-for="(item, index) in items" :key="index">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>
<script>
  export default {
    name: 'list',
    components: {},
    methods: {},
    props: ['title', 'items']
  }
</script>
