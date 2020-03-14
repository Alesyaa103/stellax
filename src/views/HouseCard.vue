<template>
  <div>
    <Header />
    <b-card-group deck class="mx-0 my-3">
      <b-card class="contentLeft shadow">
        <HouseGrade v-if="object" :address="object.Address" :grossYeild="object.Gross_rental_yield" :riskScore="object.Risk"/>
      </b-card>
      <b-card class="shadow">
        <HouseInfo v-if="object" :price="object.Price" :meters="object.Sqm" :year="object.ConstructionYear"/>
      </b-card>
    </b-card-group>
    <b-card-group deck class="mx-0 my-3">
      <b-card class="contentLeft shadow">
        <HouseInput />
      </b-card>
      <b-card class="shadow">
        <financing />
      </b-card>
    </b-card-group>
    <div class="container-fluid">
      <CashFlow />
    </div>
  </div>
</template>
<script>
import Header from "../components/Header.vue";
import HouseGrade from "../components/HouseGrade.vue";
import HouseInfo from "../components/HouseInfo.vue";
import HouseInput from "../components/HouseInput.vue";
import CashFlow from "../components/CashFlow.vue";
import Financing from "../components/Financing.vue";

export default {
  name: "HouseCard",
  components: {
    Header,
    HouseGrade,
    HouseInfo,
    HouseInput,
    CashFlow,
    Financing
  },
  data: () => ({
    object: {},
  }),
  mounted() {
    this.axios.get('HTTPS://cors-anywhere.herokuapp.com/http://35.181.35.121:81/netherlands')
      .then((res) => {
        this.object = res.data[1];
      });
  }
};

</script>
<style scoped>
.contentLeft {
  min-width: 55%;
}
.card {
  background-color: rgb(249, 249, 249);
}
</style>
