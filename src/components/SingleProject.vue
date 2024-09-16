<template>
  <div class="project" :class="{ complete : project.complete }">
    <div class="flexing">
      <div>
        <h1 @click="showDetail = !showDetail">{{ project.title }}</h1>
      </div>
      <div>
        <span class="material-symbols-outlined"> delete </span>
        <span class="material-symbols-outlined"> edit </span>
        <span class="material-symbols-outlined"> done </span>
      </div>
    </div>
    <p v-if="showDetail">{{ project.detail }}</p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: ["project"],
  setup() {
    let showDetail = ref(false);

    return { showDetail };
  },
};
</script>

<style>
h1{
    cursor: pointer;
}
.project {
  background: #ddd;
  padding: 20px;
  margin: 10px;
  border-radius: 5px;
  border-left: 6px solid red;
}
.flexing{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
span{
    margin-left: 10px;
    cursor: pointer;
}
.complete{
    border-left: 6px solid green;
}
</style>