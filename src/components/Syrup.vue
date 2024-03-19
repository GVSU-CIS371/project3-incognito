<template>
  <div class="syrup" :style="{ backgroundColor: showSyrupChoice }"></div>
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
  name: "None",
});

const showSyrupChoice = computed(()=>{ 
  const syrup = Syrups.find((syrup) => syrup.name === props.name);
  return syrup ? syrup.color : "None";
});

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
