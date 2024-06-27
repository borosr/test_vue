<script setup lang="ts">
import Btn from "@/components/Btn.vue";
import Picker from "@/components/Picker.vue";
import {ref} from "vue";

function printMsg(e: Event) {
  console.log('clicked', e)
}

let selectedPicker = ref('')
</script>

<template>
  <header>
  </header>

  <main>
    <Btn @click="printMsg">
      <span>Click me</span>
    </Btn>

    <p v-if="selectedPicker">Selected value: {{ selectedPicker }}</p>

    <Picker :options="[
        { title: 'first', value: 1 },
        { title: 'second', value: 2 }
    ]" placeholder="Pick something" v-model="selectedPicker"></Picker>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
