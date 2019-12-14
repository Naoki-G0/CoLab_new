<template>
 <div>
  <h1>Co-Lab
  </h1>
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
  <br>
  <br>
  <br>
  <NLink to="/lifescience">
   Life Science and Technology
  </NLink>
  <br>

  <NLink to="/CivilEngine">
   Civil and Environmental Engineering
  </NLink>
  <br>
  
  <NLink to="/scimath">
   School of Science - Department of Mathematics
  </NLink>
  <br>

 </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
