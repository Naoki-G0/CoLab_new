
<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      right
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-home</v-icon>
          </v-list-item-action>

          <v-list-item-content>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-contact-mail</v-icon>
          </v-list-item-action>

          <v-list-item-content>
            <v-list-item-title>Contact</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="cyan"
      dark
    >
      <v-spacer />

      <v-toolbar-title>Co-lab</v-toolbar-title>

      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
    </v-app-bar>

    <v-content>
      <v-container fluid>
        <blockquote class="display-3">Tokyo Institute of Technology</blockquote><br>
        <blockquote class="headline">School of Life Science and Technology</blockquote>


        <br><br><br>


        <div class="cyan darken-2 text-center">
          <p class="headline font-weight-bold white--text">Masuda Laboratory</p>
        </div>


         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >No photosynthesis, no life. Why don't you study</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
            We are studying molecular mechanisms  of how photosynthetic organism sense and respond to light quality and quantity to control photosynthesis.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: Photobiology / Photosynthesis / Plant physiology / Microbiology
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_masuda.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>


          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Masahiro Takinoue Laboratory</p>
  </div>


         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >DNA molecular robotics and artificial life</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                Life = information material. We develop molecular robot, DNA nanodevices, and aretificial life by molecular experiments with numerical simulations.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: DNA information devices, Molecular robots, Molecular computers / Bio-electro-mechanohybrid system, Cybernetics / Biophysics, Microfluidics, Soft matter / Artificial life, Synthetic biology
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_masuda.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>
        </v-container>
    </v-content>


    <v-footer
      color="cyan"
      app
    >
      <v-spacer />

      <span class="white--text">&copy; 2019</span>
    </v-footer>
  </v-app>
  
    
</template>

<script>
  export default {
    name: 'LayoutsDemosBaselineFlipped',
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
    }),
    message: "School of Life Science and Technology",
  }


  </script>



