<template>
  <div class="houseinput">
    <h3>Ravenue</h3>
    <div class="greenBg my-2" style="color:rgb(228, 255, 234);" >.</div>
    <div class="d-flex">
      <b-row class="my-1 mx-0" v-for="item in revenueItems" :key="item">
        <b-col>
          <label :for="`item-${item}`">{{ item }}</label>
        </b-col>
        <b-col>
          <b-form-input :id="`item-${item}`" :item="item"></b-form-input>
        </b-col>
      </b-row>
    </div>
    <h3>Expenses</h3>
    <div class="d-flex justify-content-around greenBg my-2">
      <h5>One time</h5>
      <h5>Recruting</h5>
    </div>
    <div class='d-flex'>
      <div>
        <b-row class="my-1 mx-0" v-for="item in expensesOnce" :key="item">
          <b-col>
            <label :for="`item-${item}`">{{ item }}</label>
          </b-col>
          <b-col>
            <b-form-input :id="`item-${item}`" :item="item"></b-form-input>
          </b-col>
        </b-row>
      </div>
      <div>
        <b-row class="my-1 mx-0" v-for="item in expensesOnce" :key="item">
          <b-col>
            <label :for="`item-${item}`">{{ item }}</label>
          </b-col>
          <b-col>
            <b-form-input :id="`item-${item}`" :item="item"></b-form-input>
          </b-col>
        </b-row>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HouseInput",
  data() {
    return {
      some_data: "",
      revenueItems: [
        'Annual rent',
        'Occupancy rate'
      ],
      expensesOnce: [
        'Transfer tax',
        'Mortgage closing',
        'Valuation report',
        'Notary'
      ],
      expensesRecruting: [
        'VVE',
        'Erfpacht',
        'Renovation',
        'Management',
        'Mortage'
      ]
    };
  }
};
</script>

<style scoped>
input:focus {
  border: 1px solid rgb(75, 163, 93);
  box-shadow:  0px 0px 2px 2px  rgb(75, 163, 93);
}
input {
  height: 30px;
}
.greenBg {
  background-color: rgb(228, 255, 234);
}
</style>