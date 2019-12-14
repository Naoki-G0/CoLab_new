<template>
 <div>
  <h1>Co-Lab
  </h1>
  <v-btn
      class='about-us-button'
      color="primary"
      dark
      @click.stop="dailog = true"
    >
      About us
    </v-btn>
    <br>
  <NLink to="/about">
   What is Co-Lab?
  </NLink>
  <br>
  <NLink to="/search">
   Basic Search
  </NLink>
  <br>
  <NLink to="/register">
   Register
  </NLink>
  <br>
  <NLink to="/login">
   Login
  </NLink>
  <br>
  <NLink to="/faq">
   FAQ
  </NLink>
  <br>
  <NLink to="/contact">
   Contact us
  </NLink>
  <v-card
    flat
    tile
  >
  <!--  <v-toolbar
      color="cyan"
      dark
    >
    -->
    <!--  <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>

      <v-spacer></v-spacer>
-->
      <!--
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      -->
  <!--  </v-toolbar>

    <v-container
      v-for="type in types"
      :key="type"
      class="grey lighten-4"
      fluid
    >
    -->
  <!--    <v-subheader>{{ type }}</v-subheader>

      <v-row>
        <v-spacer></v-spacer>
        <v-col
          v-for="card in cards"
          :key="card"
          cols="12"
          sm="6"
          md="4"
        >
          <v-card>
            <v-img
              :src="`https://picsum.photos/200/300?image=${getImage()}`"
              height="300px"
            >
              <span
                class="headline white--text pl-4 pt-4"
                v-text="card.title"
              ></span>
            </v-img>
            -->
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
        <v-btn color="primary" dark v-on="on">Open Dialog</v-btn>
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
                    <v-col v-for="subCategory in category.subCategories">
                      <v-checkbox
                        :id="`${category.categoryName}-${subCategory}`"
                        :value="`${category.categoryName}-${subCategory}`"
                        v-model="checkboxes"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        v-bind:label="subCategory"
                        required
                      ></v-checkbox>
                    </v-col>
                    <!--
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                  </v-row>
                  <v-row
                    class="mb-6"
                    no-gutters
                  >
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                    <v-col>
                      <v-checkbox
                        v-model="checkbox"
                        :rules="[v => !!v || 'You must agree to continue!']"
                        label="Do you agree?"
                        required
                      ></v-checkbox>
                    </v-col>
                    -->
                  </v-row>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
         <!-- <v-radio-group v-model="dialogm1" column>
           -->
           <!-- <v-radio label="Math" value="math"></v-radio>
            <v-radio label="Bahrain" value="bahrain"></v-radio>
            <v-radio label="Bangladesh" value="bangladesh"></v-radio>
            <v-radio label="Barbados" value="barbados"></v-radio>
            <v-radio label="Belarus" value="belarus"></v-radio>
            <v-radio label="Belgium" value="belgium"></v-radio>
            <v-radio label="Belize" value="belize"></v-radio>
            -->
      <!--      <v-radio label="Benin" value="benin"></v-radio>
            <v-radio label="Bhutan" value="bhutan"></v-radio>
            <v-radio label="Bolivia" value="bolivia"></v-radio>
            <v-radio label="Bosnia and Herzegovina" value="bosnia"></v-radio>
            <v-radio label="Botswana" value="botswana"></v-radio>
            <v-radio label="Brazil" value="brazil"></v-radio>
            <v-radio label="Brunei" value="brunei"></v-radio>
            <v-radio label="Bulgaria" value="bulgaria"></v-radio>
            <v-radio label="Burkina Faso" value="burkina"></v-radio>
            <v-radio label="Burma" value="burma"></v-radio>
            <v-radio label="Burundi" value="burundi"></v-radio>
            -->
        <!--  </v-radio-group>
        -->
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn 
          class = 'research-button'
          color="blue darken-3" text @click="dailog = false">Research</v-btn>
        <!--  <v-btn color="blue darken-1" text @click="dailog = false">Save</v-btn>  -->
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
 <!-- <v-btn
      color="primary"
      dark
      @click.stop="dialog = true"
    >
      トリセツ💕
    </v-btn>
    -->
  <v-dialog
      v-model="dailog"
      max-width="770"
    >
      <v-card>
        <!-- <v-card
    flat
    tile
  >
    <v-toolbar
      color="cyan"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-toolbar>

    <v-container
      v-for="type in types"
      :key="type"
      class="grey lighten-4"
      fluid
    >
      <v-subheader>{{ type }}</v-subheader>

      <v-row>
        <v-spacer></v-spacer>
        <v-col
          v-for="card in cards"
          :key="card"
          cols="12"
          sm="6"
          md="4"
        >
          <v-card>
            <v-img
              :src="`https://picsum.photos/200/300?image=${getImage()}`"
              height="300px"
            >
              <span
                class="headline white--text pl-4 pt-4"
                v-text="card.title"
              ></span>
            </v-img>

            <v-card-actions class="white justify-center">
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
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
  -->
        <v-card-title class="headline">Co-Lab とは...</v-card-title>

        <v-card-text>
          東工大内の研究室を自分の好みに応じて簡便に検索することを目的としたウェブサイトです。
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

        <!--
            <v-btn
            color="green darken-1"
            text
            @click="dialog = false"
          >
            Disagree
          </v-btn>
        -->
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
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
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
    },
}
</script>
<style scoped>
.about-us-button {
  float: right;
}
.research-button {
  float: center;
}
.v-input--selection-controls__ripple {
  color: inherit !important;
}
</style>