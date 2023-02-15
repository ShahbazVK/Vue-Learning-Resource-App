<template>
<the-header></the-header>
<!-- <stored-resources :resources="storedResources"></stored-resources> -->
<the-resources></the-resources>
</template>

<script>
// import LearningResources from './components/learning-resources/LearningResource.vue'
// import StoredResources from './components/learning-resources/StoredResources.vue'
import TheHeader from './components/layout/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';
export default {
    components: {
        // StoredResources,
        TheHeader,
        TheResources,
    },
}
</script>

<style>

</style>
