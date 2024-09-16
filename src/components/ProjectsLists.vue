<template>
    <div v-for="project in projects" :key="project.id">
        <SingleProject :project="project"/>
    </div>
</template>

<script>
import SingleProject from './SingleProject.vue';
export default {
    components : {
        SingleProject
    },
    props : [
        'projects'
    ]
}
</script>

<style>

</style>