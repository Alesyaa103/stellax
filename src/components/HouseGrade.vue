<template>
  <b-row class="h-100">
    <b-col class="no-gutter houseCard__img" :style="{backgroundImage: `url(${house.img})`}"></b-col>
    <b-col d-sm-flex flex-column justify-content-between>
      <h1 class="housegrade__title" v-if="address">{{address}}</h1>
      <div>
        <h4>Nearby:</h4>
        <p>5 bars, 3 schools, 1 hospital, 5 coffeeshops</p>
      </div>
      <div class="housegrade__ring d-xl-flex justify-content-around mt-4">
        <Ring v-if="grossYeild" :value="grossYeild" :name="nameGross"></Ring>
        <Ring v-if="riskScore" :value="riskScore" :name="nameRisk"></Ring>
      </div>
    </b-col>
  </b-row>
</template>

<script>
import Ring from "./Ring.vue";

export default {
  name: "HouseGrade",
  components: {
    Ring
  },
  props: {
    address: String,
    grossYeild: Number,
    riskScore: Number,
  },
  data() {
    return {
      nameGross: 'Gross Yeild',
      nameRisk: 'Risk Score',
      house: {
        img:
          "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60",
      }
    };
  }
};
</script>

<style scoped>
.no-gutter {
  padding-right: 0;
  padding-left: 0;
}

.housegrade__title {
  font-size: 24px;
}
.housegrade {
  border: 1px solid #c7c7c7;
  border-bottom: none;
}
.houseCard__img {
  background-size: cover;
  object-fit: fill;
  margin: 0 15px;
  background-repeat: no-repeat;
}
</style>