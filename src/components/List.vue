<template>
  <div>
    <h3>{{title}}</h3>
    <ul class="list">
      <li v-for="(item, index) in items" :key="index">
        {{ item.name }}
        <a @click="handleOnClickDelete($event, index)"><small>削除</small></a>
      </li>
    </ul>
  </div>
</template>
<script>
  export default {
    name: 'list',
    components: {},
    methods: {},
    props: ['title', 'items'],
    methods: {
      handleOnClickDelete: function(e, index) {
        e.preventDefault()
        const cityName = this.items[index].name
        if (window.confirm(`${cityName}を削除してもよろしいですか？`)) {
          this.$emit('delete-item', index)
        }
      }
    }
  }
</script>
