<template>
  <div id="app">
    <SortNum/>
    <router-view/>
  </div>
</template>


<script>
import SortNum from './components/SortNum.vue'  

export default {
  name: 'App',
  components: {
    SortNum
  }
}
</script>


