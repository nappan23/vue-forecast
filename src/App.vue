<template>
  <div id="app" class="container">
    <aside class="sub-container">
      <CityInput @submit-test="handleOnSubmit" />
      <List title="一覧" :items="cities" @delete-item="handleOnDeleteItem" />
    </aside>
    <main class="main-container">
      <p>{{ message }}</p>
      <Count :count="count" @count-up="handleOnCountUp" />
    </main>
  </div>
</template>
<script>
import store from './store';
import Count from './components/Count'
import List from './components/List'
import CityInput from './components/CityInput'
export default {
  name: 'app',
  components: {
    Count,
    List,
    CityInput
  },
  data: () => store.state,
  methods: {
    handleOnSubmit: function (city) {
      this.cities.push(
        { name: city }
      )
    },
    handleOnCountUp: function () {
      this.count++
    },
    handleOnDeleteItem: function(index) {
      this.cities.splice(index, 1)
    }
  }
}
</script>
<style>
  html {
    width: 100%;
    height: 100%;
  }
  body {
    margin: 0;
    width: 100%;
    height: 100%;
  }
  .container {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    width: 100%;
    height: 100%;
    box-sizing: content-box;
    background: #efefef;
  }
  .sub-container {
    width: 200px;
    margin: 8px 0 8px 8px;
    padding: 8px;
    background: #fff;
  }
  .main-container {
    flex: 1;
    margin: 8px;
    padding: 8px;
    background: #fff;
  }
</style>
