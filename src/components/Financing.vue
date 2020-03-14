<template>
  <div class="financing">
    <h3>Financing</h3>
    <div class="greenBg my-2" style="color:rgb(228, 255, 234);" >.</div>
    <b-row class="my-1 mx-0">
      <b-col>
        <label for="cs">Cash/Mortgage</label>
      </b-col>
      <b-col>
        <b-form-input type="text" id="cs" />
      </b-col>
    </b-row>  
    <b-row class="my-1 mx-0">
      <b-col>
        <label for="an">Annuity</label>
      </b-col>
      <b-col>
        <b-form-input type="text" id="an" />
      </b-col>
    </b-row> 
    <div class="d-flex justify-content-around">
      <span>Hypotheeksom</span>
      <span>265.000€</span>
    </div>
    <b-form-input id="type-range0" v-model="value[0]" type="range"></b-form-input>
    <div class="d-flex justify-content-around">
      <span>Rentepercentage</span>
      <span>1,85%</span>
    </div>
    <b-form-input id="type-range1" v-model="value[1]" type="range"></b-form-input>
    <div class="d-flex justify-content-around">
      <span>Doorlooprijd</span>
      <span>30jaar</span>
    </div>
    <b-form-input id="type-range2" v-model="value[2]" type="range"></b-form-input>
  </div>
</template>

<script>
export default {
  name: "Financing",
  data() {
    return {
      value: [100, 30, 80]
    };
  }
};
</script>

<style scoped>
.greenBg {
  background-color: rgb(228, 255, 234);
}
input[type="text"]:focus {
  border: 1px solid rgb(75, 163, 93);
  box-shadow:  0px 0px 2px 2px  rgb(75, 163, 93);
}
input {
  height: 30px;
}
.custom-range::-webkit-slider-thumb {
  background: rgb(75, 163, 93);
}
.fa-user-circle {
  font-size: 24px;
}

input[type="range"]::-moz-range-progress {
  background-color: rgb(75, 163, 93);
  border: 1px solid rgb(75, 163, 93);
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
}
input[type="range"]::-ms-fill-lower {
  background-color: rgb(75, 163, 93);
  border: 1px solid rgb(75, 163, 93);
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
}
input[type="range"]::-webkit-progress-value {
  background-color: rgb(75, 163, 93);
  border: 1px solid rgb(75, 163, 93);
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
}
</style>