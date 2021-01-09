<template>
  <div id="app">
    <List/>
    <Check/>
    <Plan/>
    <Usetable/>
    <Count/>
    <Arraysort/>
    <Palbum/>
    <Pass/>
  </div>
</template>

<script>
import List from '@/components/List.vue'
import Check from '@/components/Check.vue'
import Plan from '@/components/Plan.vue'
import Usetable from '@/components/Usetable.vue'
import Count from '@/components/Count.vue'
import Arraysort from '@/components/Arraysort.vue'
import Palbum from '@/components/Palbum.vue'
import Pass from '@/components/Pass.vue'
export default {
  components:{
    List,
    Check,
    Plan,
    Usetable,
    Count,
    Arraysort,
    Palbum,
    Pass
  },
  name: 'app',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
