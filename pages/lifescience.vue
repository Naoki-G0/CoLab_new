
<template>

    <v-content>
        <div class="text-right">
            <NLink to="/">  
            <v-btn rounded color="#00838F" dark>Homepage</v-btn>
            </NLink>
        </div>

      <v-container fluid>
        <br>
        <blockquote class="display-3">Tokyo Institute of Technology</blockquote><br>
        <blockquote class="headline">School of Life Science and Technology</blockquote>
        <br>
  <div class="text-left">
    <NLink to="/">  
        <v-btn rounded color="#00838F" dark>Search</v-btn>
    </NLink>
    <input v-mode="Search" placeholder="Search" style="background-color:white; width: 300px; color: black;"></v-input>
  </div>
        <br>
        <div class="cyan darken-2 text-center">
          <p class="headline font-weight-bold white--text">Masuda Laboratory</p>
        </div>

        <a href="http://www.photobiolab.bio.titech.ac.jp/~official/labhp/en/index.html" class="card-link">    
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
          </a>
            <br><br>

          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Masahiro Takinoue Laboratory</p>
  </div>

        <a href="http://www.takinoue-lab.jp/en/" class="card-link"> 
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
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_21945_takinoue.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>
          </a>
          <br><br>

          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Kajikawa Laboratory</p>
  </div>


         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >Are transposable element alive?</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                There are a huge number of transposable element (TEs) in the genome of organisms. Our aim is to elucidate the amplification mechanism of TEs.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: Transposable element / Retrotransposon / Genome evolution / Epigenetics
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_kajikawa.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>

<br><br>

          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Urabe and Hata Laboratory</p>
  </div>

         <a href="http://www.urabe-lab.bio.titech.ac.jp/" class="card-link"> 
         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >Organic chemistry - The area leading biosciences</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                Our projects include the development of new, economical, or environmentally benign organic reactions and their applcation to the preparation of pharmaceuticals.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: Organic chemistry / Synthetic chemistry / Pharmeceutical chemistry / Natural products chemistry
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_urabe_hata.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>
          </a>

<br><br>

          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Tokunaga Laboratory</p>
  </div>

         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >Visualization and quantitation of cell mechanisms</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                Based on development of techniques in molecular imaging, and quantification, our goal is the understanding of cellular dynamics and mechanisms.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: Single molecule imaging and quantification / Super-resolution microscopy / Cellular dynamic and function / Chromatin and nuclear dynamics
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_tokunaga_sogawa.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>

          <br><br>

          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Suzuki Laboratory</p>
  </div>

        <a href="http://www.suzukit.bio.titech.ac.jp/" class="card-link">
         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >Breaking genetic codes in neuronal circuit</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                Our research goal is to elucidate the molecular mechanisms underlying neuronal circuit formation and function by means of molecular neurogenetics.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: Brian / Neuron / Development / Biology
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_suzuki.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>
          </a>

                    <br><br>

          <div class="cyan darken-2 text-center">
    <p class="headline font-weight-bold white--text">Kimura Laboratory</p>
  </div>

        <a href="http://kimura-lab.bio.titech.ac.jp/index.html" class="card-link">
         <v-card
            color="#ECEFF1"
            dark
          >
            <v-row>
              <v-col cols=8>
                <v-card-title
                  class="headline black--text"
                >In vivo regulation of epigenetic dynamics</v-card-title>

                <v-card-subtitle class="subtitle black--text"> <br>
                To understand the mechanism of gene expression, we are investigating histone modification dynamics in living cells and organisms.
                </v-card-subtitle>

                 <v-card-subtitle class="subtitle font-weight-bold black--text"> <br>
                Keywords: Epigenetics / Cell nucleus / Transcription / Live cell imaging
                 </v-card-subtitle>
              </v-col>
              <v-col cols=4>
               <v-img class="ma-5" src="https://educ.titech.ac.jp/bio/eng/faculty/research_lab/img/lab_10396_kimura.jpg"></v-img>
              </v-col>
            </v-row>
          </v-card>
          </a>

        </v-container>
    </v-content>

    
</template>

<script>
  export default {
    name: 'LayoutsDemosBaselineFlipped',
    props: {
      source: String,
    },
    data: () => ({


    }),
    message: "School of Life Science and Technology",
  }


  </script>

  <style>
    .card-link{
        text-decoration: none;
    }
  </style>


