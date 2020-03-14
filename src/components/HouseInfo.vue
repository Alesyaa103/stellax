<template>
  <div v-if="meters">
    <b-table borderless :items="houseinfo"></b-table>
    <b-table borderless :items="houseparams"></b-table>
    <div class="ml-2">
      <h5>Neighborhood:</h5>
      <p> Crime level Income Business Age</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HouseInfo",
  props: {
    price: Number,
    year: Number,
    meters: Number
  },
  data() {
    return {
      houseinfo: [
        { Price: '', Square_meters: '', Bedrooms: "", Construction_Year: ''}
      ],
      houseparams: [
        {
          Dayses: 20,
          Population: 20,
          Destiny: 20,
          Days: 20,
          Energy: "D",
          Credibility: 20,
          // _cellVariants: { Dayses: "info", Population: "warning" }
        }
      ]
    };
  },
  watch: {
    price: function(val) {
      this.houseinfo[0].Price = val;
    },
    year: function(val) {this.houseinfo[0].Construction_Year = val},
    meters: function(val) {this.houseinfo[0].Square_meters = val}
  }
};
</script>

<style scoped>
/* .houseinfo {
  border: 1px solid #c7c7c7;
  border-bottom: none;
  border-left: none;
} */
.table thead th {
  vertical-align: bottom;
  border-bottom: none;
}
.table th,
.table td {
  padding: 0.75rem;
  vertical-align: top;
  border: none;
}
</style>