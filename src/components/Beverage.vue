<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer v-on:click="showCreamerChoice"/>
      </template>
      <template v-slot:mid>
        <Syrup v-on:click="showSyrupChoice"/>
      </template>
      <template v-slot:bottom>
        <Base v-on:click="showBaseChoice"/>
      </template>
    </Contents>
  </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
  isIced: boolean;
  creamer: string;
  syrup: string;
  beverage: string;
};
defineProps<Props>();
</script>
