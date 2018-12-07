<template>
  <div id="app" class="container">
    <aside class="sub-container">
      <List title="一覧" :items="cities" />
    </aside>
    <main class="main-container">
      <p>{{ message }}</p>
      <Count />
    </main>
  </div>
</template>
<script>
import store from './store';
import Count from './components/Count'
import List from './components/List'
export default {
  name: 'app',
  components: {
    Count,
    List
  },
  data: () => store.state
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
