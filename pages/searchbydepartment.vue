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
        <blockquote class="headline">Search by Department</blockquote>
      </v-container>
<v-row>    
  <v-col cols=4>
    <v-card
    class="mx-auto"
    max-width="344"
    max-height="688"
  >
    <v-img
      src="https://wallpapercave.com/wp/wp2063104.jpg"
      height="200px"
    ></v-img>

    <v-card-title>
      Civil and Environment <br> Engineering
    </v-card-title>

    <v-card-subtitle>
      School of Environment and Society <br> Department of Civil and Environmental Engineering 
    </v-card-subtitle>

    <NLink to="/CivilEngine">  
        <v-card-actions>
            <v-btn rounded color="#00838F" dark>Search</v-btn>
        </v-card-actions>
    </NLink>


      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
        Building our environment and societies, protecting life, and committing to future prosperity
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</v-col>

<v-col cols=4>
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-img
      src="https://www.marj3.com/wp-content/uploads/2019/10/f_Applied-Mathematics-1440x480.jpg"
      height="200px"
    ></v-img>

    <v-card-title>
      Mathematics
    </v-card-title>

    <v-card-subtitle>
      School of Science <br> Department of Mathematics
    </v-card-subtitle>

    <NLink to="/scimath">  
        <v-card-actions>
            <v-btn rounded color="#00838F" dark>Search</v-btn>
        </v-card-actions>
    </NLink>


      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
        Cultivate logical thinking and deep insight by attaining a grounding in and specialized knowledge of mathematics - the foundation of all human intellectual endeavors.
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</v-col>

<v-col cols=4>
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-img
      src="https://nordiclifescience.org/wp-content/public_html/2014/08/dna-structure.jpg"
      height="200px"
    ></v-img>

    <v-card-title>
      Life Science and Technology
    </v-card-title>

    <v-card-subtitle>
      School of Life Science and Technology
    </v-card-subtitle>

    <NLink to="/lifescience">  
        <v-card-actions>
            <v-btn rounded color="#00838F" dark>Search</v-btn>
        </v-card-actions>
    </NLink>


      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
        Training students of life science and technology to succeed on a global level
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</v-col>

</v-row>


<v-col cols=4>
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-img
      src="http://www.aindustrynewstoday.com/wp-content/uploads/2019/09/New-physics-might-be-evident-as-the-CERN-results-suggests.jpg"
      height="200px"
    ></v-img>

    <v-card-title>
      Physics
    </v-card-title>

    <v-card-subtitle>
      School of Science <br> Department of Physics
    </v-card-subtitle>

    <NLink to="/sciphysics">  
        <v-card-actions>
            <v-btn rounded color="#00838F" dark>Search</v-btn>
        </v-card-actions>
    </NLink>


      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
        Through deep exploration of natural laws and phenomena, we contribute to the development of science and technology
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</v-col>

</v-content>  
</template>

<script>
  export default {
    data: () => ({
      show: false,
    }),
  }
</script>

  <style>
    .btn-link{
        text-decoration: none;
    }
  </style>