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

  <v-row justify="center">
    <v-dialog v-model="category" scrollable >
      <template v-slot:activator="{ on }">
        <v-btn color="primary" dark v-on="on">Category</v-btn>
      </template>
      <v-card>
        <v-card-title>Category</v-card-title>
        <v-divider></v-divider>
        <v-card-text style="height: 300px;">
          <v-row justify="center">
            <v-expansion-panels inset>
              <v-expansion-panel
                v-for="(category, i) in categories"
                :key="i"
              >
              
                <v-expansion-panel-header>
                  {{ category.categoryName }}
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-row
                    class="mb-6"
                    no-gutters 
                  >
                    <v-col v-for="subCategory in category.subCategories" :key="subCategory">
                      <v-checkbox
                        :id="subCategory"
                        :value="subCategory"
                        v-model="checkboxes"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        v-bind:label="subCategory"
                        required

                      ></v-checkbox>
                    </v-col>
                    
                  </v-row>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
     
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn 
          class = 'research-button'
          color="blue darken-3" text @click="submit();category=false">Research</v-btn>
      
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
  <div v-for="lab in filteredLabdata" :key="lab.labname">
        <br>
        <div class="cyan darken-2 text-center">
          <p class="headline font-weight-bold white--text">{{lab.labname}}</p>
        </div>

        <blockquote class="headline">
          {{lab.department}}
        </blockquote>

        <a :href="lab.url" class="card-link" target="_blank" rel="noopener noreferer">    
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
               <v-img class="ma-5" :src="lab.photo"></v-img>
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
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

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
    this.checkboxes=selectedKeywords
  },
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
   return{
          filteredLabdata: []
         },
         {
          dialogm1: '',
         dailog: false,
         category: false,
         types: ['Places to Be', 'Places to See'],
         checkboxes: [],
         cards: ['Good', 'Best', 'Finest'],  
         categories: [
         {
          categoryName: 'Biology',
          subCategories: ['Epigenetics','Live Cell Imaging','Photobiology','Microbiology','Molecular computers',
                          'Genome evolution','Synthetic chemistry','Natural products chemistry',
                          'Super-resolution microscopy','Neuron']
         }, 
         {
          categoryName: 'Civil and Environment Engineering',
          subCategories: ['Urban planning','Urban policy','Physical modeling','Geotechnical engineering',
                          'Earthquake engineering','Education for disaster mitigation','Advance computational methods',
                          'Water environment','Water treatment','Tourism planning']
         },
         {
          categoryName: 'Mathmatics',
          subCategories: ['Knot theory','Number theory','Nonlinear partial differential equations',
                          'L-functions','Modular forms','Algebraic geometry','Partial differential equation',
                          'Manifolds','Curves and surfaces']

         },
         {
          categoryName: 'Physics',
          subCategories: ['Manifolds','Curves and surfaces','Ultrafast spectroscopy','Black hole',
                          'Nanomaterial','Metamaterial','Theoretical physics',
                          'Tracking detector','Crystal growth','Scanning probe microscopy']
        }
                      ],
         socials: [
         {
          icon: 'fab fa-facebook',
          color: 'indigo',
         },
         {
          icon: 'fab fa-linkedin',
          color: 'cyan darken-1',
         },
         {
          icon: 'fab fa-instagram',
          color: 'red lighten-3',
         },
                   ],
         }
         },

   methods: {
      getImage () {
        const min = 550
        const max = 560

        return Math.floor(Math.random() * (max - min + 1)) + min
      },
      deback (){
        console.log(this.checkboxes)
      }, 
      submit(){
        const checkboxes=this.checkboxes.join(',')
        console.log(checkboxes)
         this.filteredLabdata = labdata.filter((l) => {
      let flag=false
      l.keywords.forEach(keyword => {
        if(checkboxes.includes(keyword)) {
          flag=true
          return
        }
      })
      return flag
    })
      }
      
    },
}  
</script>

<style>

</style>