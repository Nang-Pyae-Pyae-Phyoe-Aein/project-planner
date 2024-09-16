<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="projects.length">
      <ProjectsLists :projects="projects"/>
    </div>
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import { ref } from 'vue';
import ProjectsLists from '@/components/ProjectsLists.vue';

export default {
  components : {
    ProjectsLists
  },
  setup() {
    let projects = ref([])
    let error = ref('')

    let load = async () => {
      try {
        // await new Promise((resolve, reject) => setTimeout(resolve, 2000))
        let response = await fetch('http://localhost:3000/projects')
        if (response.status === 404) throw new Error('Not Found URL!')
        let datas = await response.json()
        projects.value = datas
      }
      catch(err){
        error.value = err.message
      }
    }

    load()

    return { projects, error }
  }
}
</script>
