<template>

    <div class="supercalc">

          <!-- Section title -->
          <h2>How is your super currently invested?</h2>

          <div class="col-sm-6 hidden-md hidden-lg chart">
              <div class="clearfix donut-container">
                  <div class="donut-chart col-sm-6">

                      <!-- Doughnut chart -->
                      <vue-easy-pie-chart  percent="60"
                        :line-width="20"
                        :size="240"
                      >
                      </vue-easy-pie-chart>

                      <div class="tint"></div>

                      <!-- legend -->
                      <ul class="donut-legend">
                          <li>Growth assts: <strong class="growth">70%</strong></li>
                          <li>Defensive assts: <strong class="defensive">30%</strong></li>
                          <li>Relative risk: <strong>Medium</strong></li>
                      </ul>

                  </div>
              </div>
          </div>
      
          <div class="col-sm-6 col-md-12">
              <div class="slider row">

                  <div class="col-xs-1"></div>
                  <div class="col-xs-10 slider-container">

                      <!-- Vue slider -->
                      <vue-slider 
                          v-model="sliderValue"
                          :width="auto"
                          :height="16"
                          :dot-size="30"
                          :min="0"
                          :max="5"
                          :tooltip="false"
                          :clickable="true" 
                          :lazy="true"
                          :piecewise="true"
                      >
                      </vue-slider>

                  </div>
                  <div class="col-xs-1"></div>

              </div>

          </div>

          
          <div class="row">
            <div class="col-sm-6 col-md-12">

                <!-- Super plan details -->
                <h3 class="super-title">
                    <span      v-if="sliderValue === 0">{{superData.s0.title}}</span>
                    <span v-else-if="sliderValue === 1">{{superData.s1.title}}</span>
                    <span v-else-if="sliderValue === 2">{{superData.s2.title}}</span>
                    <span v-else-if="sliderValue === 3">{{superData.s3.title}}</span>
                    <span v-else-if="sliderValue === 4">{{superData.s4.title}}</span>
                    <span v-else-if="sliderValue === 5">{{superData.s5.title}}</span>
                    <span v-else>Aggresive</span>
                </h3>

                <div class="clearfix">
                    <div class="col-sm-5 visible-md visible-lg">
                        <div class="donut-chart">

                            <!-- small donut chart for large viewport  -->
                            <vue-easy-pie-chart  percent="60"
                              :line-width="20"
                              :size="120"
                            >
                            </vue-easy-pie-chart>

                            <!-- Change color of chart -->
                            <div class="tint"></div>

                            <!-- Explanantion about meanings of colour -->
                            <ul class="donut-legend">
                                <li>
                                    Growth assts: <strong class="growth">{{superData.s1.growth_assets}}%</strong>
                                </li>
                                <li>
                                    Defensive assts: <strong class="defensive">{{superData.s1.defensive_assets}}%</strong>
                                </li>
                                <li>
                                    Relative risk: <strong>{{superData.s1.relative_risk}}</strong>
                                </li>
                            </ul>


                        </div>
                    </div>
                  <p class="description col-md-6">
                      <span>
                          {{superData.s1.descriptions}}
                      </span>
                      
                  </p>
                    
                </div>

            </div>
         
        </div>
    </div>

</template>

<script>

import vueSlider from 'vue-slider-component'
import VueEasyPieChart from 'vue-easy-pie-chart'
import ConstantsDataset from '../data/data.json'

export default {
  name: 'supercalc',
  components: {
    vueSlider,
    VueEasyPieChart
  },
  data () {
    return {
      sliderValue: 0,
      superData: ConstantsDataset.superplan
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
