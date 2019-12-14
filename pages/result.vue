<template>
 <div>
  <h1>Result
  </h1>
  
  <NLink to="/">
   Top Page
  </NLink>
  
  <ul>
  <li v-for="lab in filteredLabdata" :key="lab.labname">
    {{ lab.labname }}
  </li>
  </ul>
 </div>
</template>

<script>
import {labdata} from "@/data/data.js"
export default {
  created: function() {

    this.filteredLabdata = labdata.filter((l) => l.category === this.$route.query.category)
    console.log('a is: ', this.filteredLabdata)
  },
  data() {
      return{
          filteredLabdata: []
          
      }
  }
}
</script>

<style>

</style>