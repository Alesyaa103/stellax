<template>
    <div class="circle">
      <div class="circle__name">{{name}}</div>
      <svg :width="88" :height="88" class="circle__svg" stroke-width="4" stroke="#3B854A">
        <circle :cx="44" :cy="44" :r="40" class="circle__progress" />
        <circle
          :cx="44"
          :cy="44"
          :r="40"
          :style="fileStyl"
          class="circle__progress circle__progress--fill"
        />
      </svg>
      <div class="percent">
        <slot>
          <span class="percent__int">{{ `${this.normalizeValue.toString().split('.')[0]}.${(this.normalizeValue.toString().split('.')[1]) ? this.normalizeValue.toString().split('.')[1] : '0'}%` }}</span>
        </slot>
      </div>
    </div>
</template>
<script>
export default {
  name: "Ring",
  props: {
    value: Number,
    name: String
  },
  data(){
    return {
      offset: ""
    };
  },
  computed: {
    normalizeValue() {
      return (typeof(this.value) == 'number') ? this.value : 0
    },
    fileStyl() {
      return {
        strokeDashoffset: this.offset,
        "--initialStroke": 80 * Math.PI,
        "--transitionDuration": "1000ms",
        "stroke-width": 4,
        stroke: "rgb(75, 163, 93)"
      };
    },
  },
  methods: {
    countNumber(v) {
      this.offset = "";
      this.initTimeoutHandler = setTimeout(() => {
        this.offset = (80 * Math.PI * (100 - v)) / 100;
      }, 100);
    }
  },
  watch: {
    normalizeValue: {
      handler: function(v) {
        this.countNumber(v);
      },
      immediate: true
    }
  }
};
</script>
<style scoped>
.circle {
  position: relative;
}
.circle__svg {
  transform: rotate(-90deg);
}
.circle__name {
  text-align: center;
  font-weight: bold;
}
.circle__progress {
  fill: none;
  stroke-opacity: 0.3;
  stroke-linecap: round;
}
.circle__progress--fill {
  --initialStroke: 0;
  --transitionDuration: 0;
  stroke-opacity: 1;
  stroke-dasharray: var(--initialStroke);
  stroke-dashoffset: var(--initialStroke);
  transition: stroke-dashoffset var(--transitionDuration) ease;
}
.percent {
  width: 100%;
  top: 60%;
  left: 50%;
  position: absolute;
  font-weight: bold;
  text-align: center;
  line-height: 2;
  transform: translate(-50%, -50%);
}

</style>