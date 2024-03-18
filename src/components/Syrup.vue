<template>
  <div class="syrup"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
type Prop = {
  name: string;
};
type Syrup = {
  name: string;
  color: string;
};
const Syrups: Syrup[] = [
  {
    name: "Vanilla",
    color: "#FFEFD5",
  },
  {
    name: "Caramel",
    color: "#DAA520",
  },
  {
    name: "Hazelnut",
    color: "#6B4423",
  },
];

const props = withDefaults(defineProps<Prop>(), {
  currentSyrup: string,
});

const showSyrupChoice = computed(()=>{ 
  return Syrups.find(syrup => syrup.name === props.currentSyrup);
});

const changeStyle = computed(() => { syrup: props.color});
</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
