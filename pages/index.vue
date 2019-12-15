<template>
 <div class="example">
  <!-- <img src="https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg" /> -->
  
  <p>Co-Lab</p>
  
  <form method="get" action="https://www.titech.ac.jp/english/">
  <input class="main-search" type="text" id="name" name="name" placeholder="Freeword" autocomplete="off" required
       minlength="1" maxlength="25" size="30">
  </form>

  <v-btn class="category-button" color="primary" dark @click="opencategory">Category</v-btn>
  <v-btn
      class='about-us-button'
      color="primary"
      dark
      @click.stop="dailog = true"
    >
      About us
    </v-btn>

  <v-row justify="center">
    <v-dialog v-model="category" scrollable >
      <v-card>
        <v-card-title>Category</v-card-title>
        <v-divider></v-divider>
        <v-card-text style="height: 500px;">
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
        <v-card-actions >
          <v-btn 
          class = 'research-button'
          color="blue darken-3" 
          height="80"
          text @click="submit">Research</v-btn>
      
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
 
  <v-dialog
      v-model="dailog"
      max-width="770"
    >
      <v-card>
       
        <v-card-title class="headline">Co-Lab とは...</v-card-title>

        <v-card-text>
          東工大内の研究室を自分の好みに応じて簡便に検索することを目的としたウェブサイトです。
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

       
          <v-btn
            color="green darken-1"
            text
            @click="dailog = false"
          >
            OK
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
 </div>
</template>

<script>
import {labdata} from "@/data/data.js"
import Logo from '~/components/Logo.vue'

import VuetifyLogo from '~/components/VuetifyLogo.vue'


export default {
  created: function() {
    // `this` は vm インスタンスを指します
    console.log('a is: ', labdata)

    const filteredLabdata = labdata.filter((l) => l.category === "生物学")
    console.log('a is: ', filteredLabdata)
  },
  components: {
    Logo,
    VuetifyLogo
  },
     layout:"top",
     data () {
      return {
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
      opencategory (){
        console.log(this.checkboxes)

        this.category =true
      },
      submit(){
        const checkboxes=this.checkboxes.join(',')
        this.$router.push(`/result_keywords?keywords=${checkboxes}`)
      }
      
    },
 
}
</script>


<style>
 .example {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 100px;
    width: 100%;
    height: 100vh;
    background: url('https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg') no-repeat center center;
    background-size: cover;
  }

.example p {
  position: relative;
  color: white;/*文字は白に*/
  font-weight: bold; /*太字に*/
  font-size: 9em;/*サイズ2倍*/
  margin:0;
  padding:0;
  /*文字の装飾は省略*/
  }

.example a:hover{/*カーソルを当てたとき*/
  background: rgba(255, 255, 255, 0.3);/*背景を半透明に*/
  }

.example img {
  width: 100%;
  }

label {
    display: block;
    font: 1rem 'Fira Sans', sans-serif;
}

input.main-search {
    position: relative;
    margin: .4rem 0;
    border: solid black 2px; /*線で囲う*/
    font-size: 27px;/*文字サイズ*/  
    background-color:white;
    color: black;/*文字色*/
}

.category-button {
  margin-top: 20px;
}
.about-us-button {
  margin-top: 50px;
}
.research-button {
     float: center;
}
.v-input--selection-controls__ripple  {
    color:black  inherit
}


</style>
