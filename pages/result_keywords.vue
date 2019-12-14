<template>
 <div>
    <v-content>
        <div class="text-right">
            <NLink to="/">  
            <v-btn rounded color="#00838F" dark>Homepage</v-btn>
            </NLink>
        </div>

      <v-container fluid>
        <br>
        <blockquote class="display-3">Tokyo Institute of Technology</blockquote><br>
        <br>
  <div class="text-left">
    <NLink to="/">  
        <v-btn rounded color="#00838F" dark>Search</v-btn>
    </NLink>
  </div>
  <div v-for="lab in filteredLabdata" :key="lab.labname">
    <blockquote class="headline">School of Life Science and Technology</blockquote>
        <br>
        <div class="cyan darken-2 text-center">
          <p class="headline font-weight-bold white--text">{{lab.labname}}</p>
        </div>

        <a :href="lab.photo" class="card-link" target="_blank" rel="noopener noreferer">    
         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >{{lab.title}}</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                 {{lab.subtitle}}
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: {{lab.keywords.join(' / ')}}
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" :src="lab.url"></v-img>
              </v-col>
            </v-row>
          </v-card>
          </a>
  </div>
        </v-container>
    </v-content>
 </div>
</template>

<script>
import {labdata} from "@/data/data.js"
export default {
  created: function() {
    console.log(this.$route.query)
    const selectedKeywords=this.$route.query.keywords.split(',')
    console.log(selectedKeywords)
    this.filteredLabdata = labdata.filter((l) => {
      let flag=false
      l.keywords.forEach(keyword => {
        if(selectedKeywords.includes(keyword)) {
          flag=true
          return
        }
      })
      return flag
    })
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