<template>
  <div class="project">
    <h1 @click="showDetail = !showDetail">{{ project.title }}</h1>
    <p v-if="showDetail">{{ project.detail }}</p>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  props: ["project"],
  setup(){
    let showDetail = ref(false)

    return { showDetail }
  }
};
</script>

<style>
.project{
    background: #ddd;
    padding: 20px;
    margin: 10px;
    border-radius: 5px;
}
</style>