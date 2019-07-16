<template>
    <div class="container">
        <h1>{{ msg }}</h1>
        <form class="simple-form">
        <div class="form">
            <label class="label">Family Details</label>
            <label class="label">(Please choose...)</label>
            <div class="columns">
            <div class="column">
              <div class="text">
                <label class="paragraph">What are the hours of 'recognised activity' undertaken in a fortnight under normal circumstances by the parent who does the least activity?</label>
              </div>
              <div class="dropdown">
                <select class="select" v-model="hoursselect">
                  <option>0 - 7 hours</option>
                  <option>8 - 16 hours</option>
                  <option value="default">17 - 48 hours</option>
                  <option>49+ hours</option>
                </select>
              </div>
            </div>

            <div class="column">
              <div class="text">
                <label class="paragraph">Which of the below is the best reflection of your family circumstances ?</label>
              </div>
              <div class="dropdown">
                <select class="select" v-model="workselect">
                  <option value="default">Couple, both working full time</option>
                  <option>Couple, one working full time, one working part time</option>
                  <option>Couple, one working, one not working</option>
                  <option>Couple, both not working</option>
                  <option>Sole parent, working full time</option>
                  <option>Sole parent, working part time</option>
                  <option>Sole parent, not working</option>
                  <option>Other</option>
                </select>
              </div>
            </div>
            </div>

            <div class="columns">
              <div class="column">
                <div class="text">
                  <label class="paragraph">How many children do you have (or will have) in long day care?</label>
                </div>

                <div class="dropdown">
                  <select class="select" v-model="childselect">
                    <option value="default">1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                  </select>
                </div>
              </div>

              <div class="column">
                <div class="text">
                  <label class="paragraph">What is your combined family income that you report to Centrelink? (nearest $3,000)</label>
                </div>
                <div class="slider">
                  <label>$40,000</label>
                  <input id="sliderWithValue" class="sliderbar" min="40000" max="400000" value="100000" step="1000" type="range">
                  <label>$400,000</label>
                </div>
                <div class="slider">
                  <output for="sliderWithValue">100000</output>
                  <input input_html="{:value=>&quot;100000&quot;}" type="hidden" value="133000" name="calculator[income]" id="calculator_income">
                </div>
              </div>
            </div>
          
          <div class="columns">
            <div class="column">
              <div class="text">
                <label class="paragraph">Is your FY2019 income greater than $186,958?</label>
              </div>
              <div class="dropdown">
                  <select class="select" v-model="incomeselect">
                    <option value="default">No</option>
                    <option>Yes</option>
                  </select>
                </div>
            </div>
          </div>

          <label class="label">OR</label>
          <label class="label">Enter entitlement</label>
          

        </div>
        </form>
    </div>
</template>

<script>
export default {
  name: 'Form',
  props: {
    msg: String
  },
  data: () => ({
    hoursselect: 'default',
    workselect: 'default',
    childselect: 'default',
    incomeselect: 'default'
  })
}
</script>



