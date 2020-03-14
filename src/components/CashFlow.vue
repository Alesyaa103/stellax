<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-xl-12">
        <h2>Cash flow</h2>
        <b-table class="house-table" striped hover :items="items"></b-table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CashFlow",
  data() {
    return {
      items: [
        {
          one_time: "Revenue",
          1: 1000,
          2: 1000,
          3: 1000,
          4: 1000,
          5: 1000,
          6: 1000,
          7: 1000,
          8: 1000,
          9: 1000,
          10: 1000
        },
        {
          one_time: "Expenses",
          1: 1000,
          2: 1000,
          3: 1000,
          4: 1000,
          5: 1000,
          6: 1000,
          7: 1000,
          8: 1000,
          9: 1000,
          10: 1000
        },
        {
          one_time: "Cash flow",
          1: 1000,
          2: 1000,
          3: 1000,
          4: 1000,
          5: 1000,
          6: 1000,
          7: 1000,
          8: 1000,
          9: 1000,
          10: 1000
        }
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.fa-user-circle {
  font-size: 24px;
}
</style>