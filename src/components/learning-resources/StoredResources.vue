<template>
<ul>
    <learning-resource v-for="(res,index) in resources" :key="index" :title="res.title" :description="res.description" :link="res.link" :id="res.id"></learning-resource>
</ul>
</template>

<script>
// import LearningResource from './learning-resources/LearningResource.vue';
import LearningResource from './LearningResource.vue';
export default {
    components:{
        LearningResource
    },
    inject: ['resources'],
}
</script>

<style>

</style>
