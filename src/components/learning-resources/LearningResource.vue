<template>
<li>
    <base-card>
        <header>
            <h3>{{ title }}</h3>
            <base-button mode="flat" @click="deleteResource(id)">Delete</base-button>
        </header>
        <p>{{ description }}</p>
        <nav>
            <a :href="link">View Resources </a>
        </nav>
    </base-card>
</li>
<hr>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue'
export default {
  components: { BaseButton },
  inject:['deleteResource'],
    props: [
        'id',
        'title',
        'description',
        'link'
    ]
}
</script>

<style>
* {
    list-style: none;
    text-align: center;
}
</style>
