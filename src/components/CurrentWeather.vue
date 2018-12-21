<template>
  <div>
    <div>{{city}}</div>  
    <div v-if="!current">
      loading...
    </div>
    <table v-else>
      <thead>
      <tr>
        <th>天気</th>
        <th>最高気温</th>
        <th>最低気温</th>
      </tr>
      </thead>
      <tbody>
      <tr>
        <td>{{current.weather[0].main}}</td>
        <td>{{current.main.temp_max}}</td>
        <td>{{current.main.temp_min}}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
  export default {
    name: 'currentWeather',
    components: {},
    data: function () {
      return {
        current: null
      }
    },
    props: ['city']
  }
</script>
<style>
</style>
