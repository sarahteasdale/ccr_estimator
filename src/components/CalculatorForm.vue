<template>
<v-container fluid grid-list-md>
  <v-layout v-bind="binding">
    <v-flex d-block xs12 mb-2>
      <!-- Family Details with a hover and changing text colour (text does not stay blue when the viewer is using the drop down menus) 
           Reformates to two columns (with Enter entitlements) when the screen is larger than a small screen, text elements inside reformate
           into rows when the screen is larger than a small screen -->
      <v-hover>
        <v-card  hover
          color="white"
          @mouseenter="e => e.target.classList.toggle('blue--text')" @mouseleave="e => e.target.classList.toggle('blue--text')"
        >
          <v-card-title primary class="title">{{ subtitle }}</v-card-title>
          <v-container pa-0>
            <v-layout v-bind="binding2">

              <v-flex xs12>
                <v-container pt-0 pb-0 id="selectHours">
                  <v-card-text>{{ questionOne }}</v-card-text>
                  <v-select
                    :items="selectHours"
                    label="Please Select"
                    solo
                  ></v-select>
                </v-container>
              </v-flex>

                <v-flex xs12>
                  <v-container pt-0 pb-0 id="selectWorking">
                    <v-card-text>{{ questionTwo }}</v-card-text>
                    <v-select
                      :items="selectWorking"
                      label="Please Select"
                      solo
                    ></v-select>
                  </v-container>
                </v-flex>

            </v-layout>
          </v-container>

          <v-container pa-0>
            <v-layout v-bind="binding2">

              <v-flex xs12>
                <v-container pt-0 pb-0 id="selectChild">
                  <v-card-text>{{ questionThree }}</v-card-text>
                  <v-select
                    :items="selectChild"
                    label="Please Select"
                    solo
                  ></v-select>
                </v-container>
              </v-flex>


              <v-flex xs12>
                <v-container pt-0 pb-0 id="enterDollar">
                  <v-card-text>{{ questionFour }}</v-card-text>
                  <v-text-field
                    label="Please Enter Amount"
                    prefix="$"
                    solo
                  ></v-text-field>
                </v-container>
              </v-flex>

            </v-layout>
          </v-container>

          <v-container pa-0>
            <v-layout v-bind="binding2">
              <v-flex xs6>
                <v-container pt-0 pb-0 id="selectOption">
                  <v-card-text>{{ questionFive }}</v-card-text>
                  <v-select
                    :items="selectOption"
                    label="Please Select"
                    solo
                  ></v-select>
                </v-container>
              </v-flex>
            </v-layout>
          </v-container>
          
        </v-card>
      </v-hover>
    </v-flex>

    <!-- Enter entitlement with a customised hover effect 
         Same reformating as Family Details-->
    <v-flex xs12 mb-2>
      <v-hover>
        <v-card slot-scope="{ hover }"
          :class="`elevation-${hover ? 20 : 1}`" 
          class="mx-auto"
          color="white"
        >
          <v-card-title primary class="title">{{ subtitleTwo }}</v-card-title>

          <v-container pa-0>
            <v-layout v-bind="binding2">

              <v-flex xs12>
                <v-container pt-0 pb-0 id="enterHours">
                  <v-card-text>{{ questionSix }}</v-card-text>
                  <v-text-field
                    label="Please Enter"
                    suffix="hours"
                    solo
                  ></v-text-field>
                </v-container>
              </v-flex>

              <v-flex xs12>
                <v-container pt-0 pb-0 id="enterPercentage">
                  <v-card-text>{{ questionSeven }}</v-card-text>
                  <v-text-field
                    label="Please Enter"
                    suffix="%"
                    solo
                  ></v-text-field>
                </v-container>
              </v-flex>

            </v-layout>
          </v-container>

        </v-card>
      </v-hover>
    </v-flex>
  </v-layout>

  <!-- Details for Children with customised hover effect
       Reformates into fives cards in a row when the screen is a large screen size, text elements inside reformate into one coloumns when
       the screen size is a large screen size -->
  <v-container fluid>
  <v-layout v-bind='binding3'>
    <v-flex  d-block xs12 v-for="i in 5" :key="`2${i}`">
      <v-hover>
        <v-card slot-scope="{ hover }"
          :class="`elevation-${hover ? 20 : 1}`" 
          class="mx-auto"
          color="white"
        >
          <v-card-title primary class="title">Details for Child</v-card-title>
            
            <v-flex xs12>
              <v-container pa-0>
                <v-layout v-bind="binding4">
                  <v-flex xs6>
                    <v-container pt-0 pb-0 id="selectAge">
                      <v-card-text>{{ questionEight }}</v-card-text>
                      <v-select
                        :items="selectAge"
                        label="Please Select"
                        solo
                      ></v-select>
                    </v-container>
                  </v-flex>

                  <v-flex xs6>
                    <v-container pt-0 pb-0 id="selectDays">
                      <v-card-text>{{ questionNine }}</v-card-text>
                      <v-select
                        :items="selectDays"
                        label="Please Select"
                        solo
                      ></v-select>
                    </v-container>
                  </v-flex>
                </v-layout>
              </v-container>

            </v-flex>

            <v-flex xs12>
              <v-container pa-0>
                <v-layout v-bind="binding4">
                  <v-flex xs6>
                    <v-container pt-0 pb-0 id="enterHoursPC">
                      <v-card-text>{{ questionTen }}</v-card-text>
                      <v-text-field
                        label="Please Enter"
                        suffix="hours"
                        solo
                      ></v-text-field>
                    </v-container>
                  </v-flex>

                  <v-flex xs6>
                    <v-container pt-0 pb-0 id="enterFees">
                      <v-card-text>{{ questionEleven }}</v-card-text>
                      <v-text-field
                        label="Please Enter"
                        prefix="$"
                        solo
                      ></v-text-field>
                    </v-container>
                  </v-flex>
                </v-layout>
              </v-container>

            </v-flex>

        </v-card>
      </v-hover>
    </v-flex>
  </v-layout>
  </v-container>

  <v-flex xs12>
    <v-card color="white">
      <v-btn block color="blue" dark>Calculate</v-btn>
    </v-card>
  </v-flex>


</v-container>




</template>

<script>
export default {
  name: 'CalculatorForm',
     data () {
      return {
        subtitle: 'Family Details',
        questionOne: "What are the hours of 'recognised activity' undertaken in a fortnight under normal circumstances by the parent who does the least activity?",
        selectHours: ['0 - 7 hours', '8 - 16 hours', '17 - 48 hours', '49+ hours'],
        questionTwo: "Which of the below is the best reflection of your family circumstances ?",
        selectWorking: ['Couple, both working full time', 'Couple, one working full time, one working part time', 
                        'Couple, one working, one not working', 'Couple, both not working', 'Sole parent, working full time', 
                        'Sole parent, working part time', 'Sole parent, not working', 'Other'],
        questionThree: "How many children do you have (or will have) in long day care?",
        selectChild: ['1', '2', '3', '4', '5'],
        questionFour: "What is your combined family income that you report to Centrelink? (nearest $3,000)",
        questionFive: "Is your FY2019 income greater than $186,958?",
        selectOption: ['Yes', 'No'],
        
        subtitleTwo: 'Enter entitlement',
        questionSix: "Weekly Hours",
        questionSeven: "Percentage",

        questionEight: "Age",
        selectAge: ['Up to 12 mths', '1 Year', '2 Years', '3 Years', '4 Years', '5+ Years'],
        questionNine: "Days per week",
        selectDays: ['1', '2', '3', '4', '5'],
        questionTen: "Hours per Day",
        questionEleven: "Daily Fee",
        
      }
    },
     computed: {
      binding () {
        const binding = {}

        if (this.$vuetify.breakpoint.smAndDown) binding.column = true

        return binding
      },
      binding2 () {
        const binding2 = {}

        if (this.$vuetify.breakpoint.xsOnly) binding2.column = true
        if (this.$vuetify.breakpoint.smAndDown) binding2.row = true
        if (this.$vuetify.breakpoint.mdAndUp) binding2.column = true


        return binding2
      },
      binding3 () {
        const binding3 = {}

        if (this.$vuetify.breakpoint.mdAndDown) binding3.column = true

        return binding3
      },

      binding4 () {
        const binding4 = {}

        if (this.$vuetify.breakpoint.xsOnly) binding4.column = true
        if (this.$vuetify.breakpoint.mdAndDown) binding4.row = true
        if (this.$vuetify.breakpoint.lgAndUp) binding4.column = true


        return binding4
      },
     }
}
</script>



<style scoped>


.title {
  color: #9C897A;
}
</style>
