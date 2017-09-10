<template>
  <div id="app">
    <div class="container">
      <div class="card">

          <!-- Header of the card -->
          <div class="header">
              <span class="logo">
                <img src="https://www.amp.com.au/super/supersimulator/images/amp-logo@2x.png">
              </span>
              <span>
                My super simulator
              </span>
              
          </div>
          <!-- end header -->

        <!-- calculator -->
        <supercalc></supercalc>

      </div>
      
    </div>
  </div>
</template>

<script>
import Supercalc from './components/Supercalc'

export default {
  name: 'app',
  components: {
    Supercalc
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
