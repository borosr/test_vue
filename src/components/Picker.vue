<script setup lang="ts">
import {ref} from "vue";

defineProps<{
  options: {
    title: string
    value: any
  }[],
  placeholder: string
}>()

let model = defineModel()
let show = ref(false)

</script>

<template>
  <div class="nice-picker">
    <span class="placeholder" v-if="placeholder" @click="show = !show">{{ placeholder }}</span>
    <div class="elements" v-show="show">
      <span v-for="o in options" @click="model = o.value; show = false" :key="JSON.stringify(o)">{{ o.title }}</span>
    </div>
  </div>
</template>

<style scoped>
.nice-picker {
  background-color: #888888;
  color: #181818;
  border-radius: 5px;
  cursor: pointer;

  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;

  .placeholder {
    width: 200px;
    &:hover {
      background-color: #555555;
    }
  }

  .elements {
    display: flex;
    flex-flow: column;
    background-color: #888888;
    color: #181818;
    width: 200px;
    span:hover {
      background-color: #555555;
    }
  }
}
</style>
