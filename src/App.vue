<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.png"/>
  </header>

  <main>
    <tbody class="center">
      <tr>
        <td >
          <div class="lower_val">
            <input type="checkbox" id=0 value=0.01 v-model="openedBoxes">
            <label for="00"> $0.01</label><br>

            <input type="checkbox" id=1 value=1 v-model="openedBoxes">
            <label for="1"> $1</label><br>

            <input type="checkbox" id=2 value=5 v-model="openedBoxes">
            <label for="2"> $5</label><br>

            <input type="checkbox" id=3 value=10 v-model="openedBoxes">
            <label for="3"> $10</label><br>

            <input type="checkbox" id=4 value=25 v-model="openedBoxes">
            <label for="4"> $25</label><br>

            <input type="checkbox" id=5 value=50 v-model="openedBoxes">
            <label for="5"> $50</label><br>

            <input type="checkbox" id=6 value=75 v-model="openedBoxes">
            <label for="6"> $75</label><br>

            <input type="checkbox" id=7 value=100 v-model="openedBoxes">
            <label for="7"> $100</label><br>

            <input type="checkbox" id=8 value=200 v-model="openedBoxes">
            <label for="8"> $200</label><br>

            <input type="checkbox" id=9 value=300 v-model="openedBoxes">
            <label for="9"> $300</label><br>

            <input type="checkbox" id=10 value=400 v-model="openedBoxes">
            <label for="10"> $400</label><br>

            <input type="checkbox" id=11 value=500 v-model="openedBoxes">
            <label for="11"> $500</label><br>

            <input type="checkbox" id=12 value=750 v-model="openedBoxes">
            <label for="12"> $750</label><br>
          </div>
        </td>
        <td class="padder"></td>
        <td>
          <div class="upper_val">
            <input type="checkbox" id=13 value=1000 v-model="openedBoxes">
            <label for="13"> $1,000</label><br>

            <input type="checkbox" id=14 value=5000 v-model="openedBoxes">
            <label for="14"> $5,000</label><br>

            <input type="checkbox" id=15 value=10000 v-model="openedBoxes">
            <label for="15"> $10,000</label><br>

            <input type="checkbox" id=16 value=25000 v-model="openedBoxes">
            <label for="16"> $25,000</label><br>

            <input type="checkbox" id=17 value=50000 v-model="openedBoxes">
            <label for="17"> $50,000</label><br>

            <input type="checkbox" id=18 value=75000 v-model="openedBoxes">
            <label for="18"> $75,000</label><br>

            <input type="checkbox" id=19 value=100000 v-model="openedBoxes">
            <label for="19"> $100,000</label><br>

            <input type="checkbox" id=20 value=200000 v-model="openedBoxes">
            <label for="20"> $200,000</label><br>

            <input type="checkbox" id=21 value=300000 v-model="openedBoxes">
            <label for="21"> $300,000</label><br>

            <input type="checkbox" id=22 value=400000 v-model="openedBoxes">
            <label for="22"> $400,000</label><br>

            <input type="checkbox" id=23 value=500000 v-model="openedBoxes">
            <label for="23"> $500,000</label><br>

            <input type="checkbox" id=24 value=750000 v-model="openedBoxes">
            <label for="24"> $750,000</label><br>

            <input type="checkbox" id=25 value=1000000 v-model="openedBoxes">
            <label for="25"> $1,000,000</label><br>
          </div>
        </td>
      </tr>
    </tbody>
    <div class="wrapper">
      <button class="button" id="offer" v-on:click="get_offer()">Get Deal</button>
      <h1>Your Deal is ${{deal}}</h1>
    </div>
  </main>
</template>


<script>
  export default {
    data() {
      return{
        openedBoxes: [],
        deal: null
      }
    },
    methods: {
      get_offer: function(){
        var total_val = 0;
        console.log(this.openedBoxes)
        for (var i in this.openedBoxes){
          total_val += parseFloat(this.openedBoxes[i])
        }
        const cases_left = (26 - this.openedBoxes.length)

        var expected_val = (3418416.01 - total_val) / cases_left
        var offer = 12275.30 + (.748 * expected_val) + (-2714.74 * cases_left) + (.0000006986 * expected_val**2) + ( 32.623 * cases_left**2)

        this.deal = Math.round(offer)
      }
    }
  }
</script>


<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  .lower_val{
    font-family: Copperplate;
    display: block;
    font-size: 40px;
    background-color: rgb(189, 183, 107);
    color: green;
    outline: 5px solid;
    outline-color: DarkGoldenRod;
    padding: 2rem;
    border: .5rem;
    border-radius: 25px;

  }

  .upper_val{
    font-family: Copperplate;
    display: block;
    font-size: 40px;
    background-color: rgb(189, 183, 107);
    color: red;
    outline: 5px solid;
    outline-color: DarkGoldenRod;
    padding: 2rem;
    border: .5rem;
    border-radius: 25px;

  }

  .padder{
    display: block;
    font-size: 40px;
    color: red;
    padding: 8rem;
  }

  .center{
    margin: auto;
    width: 50%;
  }

  header .wrapper {

    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  input{

    width: 1.5rem;
    height: 1.5rem;
  }

  button {
    margin-top: 3rem;
    font-size: 50px;
    margin-bottom: 3rem;
  }

  main {
    margin-left: auto;
    margin-right: auto;
  }

  h1 {
    outline-color: DarkGoldenRod;
    outline: 5px solid;
    color: gold;
    height: 4rem;
    width: auto;
    font_size: 80px;
  }
}
</style>
