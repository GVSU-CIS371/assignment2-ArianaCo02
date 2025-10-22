<template>
  <div>
    <!-- Beverage Display -->
    <Beverage
      :isIced="currentTemp === 'Cold'"
      :creamer="currentCreamer"
      :syrup="currentSyrup"
      :base="currentBase"
    />

    <!-- Temperature Options -->
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
    </ul>

    <!-- Creamer Options -->
    <h3>Creamer:</h3>
    <ul>
      <li v-for="c in creamers" :key="c">
        <label>
          <input type="radio" name="creamer" v-model="currentCreamer" :value="c" />
          {{ c }}
        </label>
      </li>
    </ul>

    <!-- Syrup Options -->
    <h3>Syrup:</h3>
    <ul>
      <li v-for="s in syrups" :key="s">
        <label>
          <input type="radio" name="syrup" v-model="currentSyrup" :value="s" />
          {{ s }}
        </label>
      </li>
    </ul>

    <!-- Base Beverage Options -->
    <h3>Base Beverage:</h3>
    <ul>
      <li v-for="b in bases" :key="b">
        <label>
          <input type="radio" name="base" v-model="currentBase" :value="b" />
          {{ b }}
        </label>
      </li>
    </ul>
  </div>
</template>


<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";

// New option lists
const creamers = ["No Creamer", "Milk", "Cream", "Half & Half"];
const syrups = ["No Syrup", "Vanilla", "Caramel", "Hazelnut"];
const bases = ["Coffee", "Green Tea", "Black Tea"];

// Selected options
const currentCreamer = ref("No Creamer");
const currentSyrup = ref("No Syrup");
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
