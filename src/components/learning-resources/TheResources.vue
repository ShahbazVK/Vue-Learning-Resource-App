<template>
<base-card>
    <base-button mode="flat" :style="{backgroundColor:selectedTab==='stored-resources'?'':'gray'}" @click="setSelectedTab('stored-resources')">Stored Resources</base-button>
    <base-button mode="flat" :style="{backgroundColor:selectedTab==='add-resources'?'':'gray'}" @click="setSelectedTab('add-resources')">Add Resource</base-button>
</base-card>
<keep-alive>
    <component :is="selectedTab"></component>
</keep-alive>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue'
import BaseCard from '../UI/BaseCard.vue'
import StoredResources from './StoredResources.vue'
// import AddResource from './AddResource.vue'
import AddResources from './AddResources.vue'
export default {
    components: {
        BaseCard,
        BaseButton,
        AddResources,
        StoredResources,
    },
    data() {
        return {
            selectedTab: 'stored-resources',
            storedResources: [{
                    id: 'official-guide',
                    title: 'Official Guide',
                    description: 'The official Vue JS documentation',
                    link: 'https://vuejs.org'
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Learn To google',
                    link: 'https://google.com'
                },
            ]
        }
    },
    provide() {
        return {
            resources: this.storedResources,
            addResource: this.addResource,
            deleteResource:this.removeResource,
        }
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab
        },
        addResource(title, description, link) {
            const newResource = {
                id: new Date().toISOString(),
                title: title,
                description: description,
                link: link
            }
            this.storedResources.unshift(newResource)
            this.selectedTab = 'stored-resources'
        },
        removeResource(resId){
            const resIndex=this.storedResources.filter(res=>res.id!==resId)
            this.storedResources.splice(resIndex,1)
        }
    }
}
</script>

<style>

</style>
