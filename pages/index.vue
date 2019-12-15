<template>
 <div class="example">
  <!-- <img src="https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg" /> -->
  
  <p>Co-Lab</p>

  <form method="get" action="http://localhost:3000/result">
  <input class="main-search" type="text" id="name" name="name" placeholder="Freeword" autocomplete="off" required
       minlength="1" maxlength="25" size="30">
  </form>
  <NLink to="/result?category=生物学" tag="button">生物学</NLink>
  <NLink to="/result?category=物理学" tag="button">物理学</NLink>

  <NLink to="/lifescience">
   Result model
  </NLink>

  <v-btn
      class='about-us-button'
      color="primary"
      dark
      @click.stop="dailog = true"
    >
      About us
    </v-btn>
    <v-card
    flat
    tile
  >
 
              <v-btn
                v-for="(social, i) in socials"
                :key="i"
                :color="social.color"
                class="white--text"
                fab
                icon
                small
              >
                <v-icon>{{ social.icon }}</v-icon>
              </v-btn>

          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
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
                        :id="`${category.categoryName}-${subCategory}`"
                        :value="`${category.categoryName}-${subCategory}`"
                        v-model="checkboxes"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        v-bind:label="subCategory"
                        required
                        @click="deback"
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
          color="blue darken-3" text @click="submit">Research</v-btn>
      
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
          categoryName: 'Math',
          subCategories: ['ベクトル解析','幾何学']
        }, 
        {
          categoryName: 'Chemistory',
          subCategories: ['有機化学','物理化学']
        },
        {
          categoryName: 'Biology',
          subCategories: ['分子生物学']

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
        this.$router.push(`/result_keywords?keywords=${checkboxes}`)
      }
      
    },
 
}
</script>


<style>
 .example {
  /* position: relative; */
    width: 100%;
    height: 100%;
    left: 0;
    position: absolute;
    background: url('https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg') no-repeat center center;
    background-size: cover;
  }

.example p {
  position: absolute;
  color: white;/*文字は白に*/
  font-weight: bold; /*太字に*/
  font-size: 10em;/*サイズ2倍*/
  top: 30%;
  left: 50%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
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
    position: absolute;
    top: 45.3%;
    left: 30%;
    margin: .4rem 0;
    border: solid black 2px; /*線で囲う*/
    font-size: 33px;/*文字サイズ*/
    background-color:white;
    color: black;/*文字色*/
}

.about-us-button {
    position: absolute;
    top: 40%;
    left: 70%;
}
.research-button {
    float: center;
}
.v-input--selection-controls__ripple  {
    color:black  inherit
}


</style>
