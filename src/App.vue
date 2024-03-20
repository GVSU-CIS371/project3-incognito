<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" :beverage="currentBase" :creamer="currentCreamer" :syrup="currentSyrup"/>
    <ul>
      <li>
      <p>
        <label> Temperature: </label>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="Temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </p>
      <p>
      <label> Creamer: </label>
        <template v-for="creamer in creamers" :key="creamer">
          <label>
            <input
              type="radio"
              name="Creamer"
              :id="`r${creamer}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            {{ creamer }}
          </label>
        </template>
      </p>
      <p>
      <label> Syrup: </label>
        <template v-for="syrup in syrups" :key="syrup">
          <label>
            <input
              type="radio"
              name="Syrup"
              :id="`r${syrup}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup }}
          </label>
        </template>
      </p>
      <p>
      <label> Base Beverage: </label>
        <template v-for="beverage in baseBeverage" :key="beverage">
          <label>
            <input
              type="radio"
              name="Base Beverage"
              :id="`r${beverage}`"
              :value="beverage"
              v-model="currentBase"
            />
            {{ beverage }}
          </label>
        </template>
      </p>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
//import Creamer from "./components/Creamer.vue";
//import Syrup from "./components/Syrup.vue";
//import Base from "./components/Base.vue";
// Define reactive data
const temps = ref(["Hot", "Cold"]);
const currentTemp = ref("Hot");
const creamers = ref(["None", "Milk", "Cream", "Half & Half"]);
const currentCreamer = ref("None");
const syrups = ref(["None", "Vanilla", "Caramel", "Hazelnut"]);
const currentSyrup = ref("None");
const baseBeverage = ref(["Coffee", "Green Tea", "Black Tea"]);
const currentBase = ref("Coffee");
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
