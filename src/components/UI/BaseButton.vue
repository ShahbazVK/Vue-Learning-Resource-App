<template>
<button :type="type" :class="mode">
    <slot></slot>
</button>
</template>

<script>
export default {
    props: ['type', 'mode']
}
</script>

<style scoped>
.flat {
    background-color: purple;
    color: white;
    padding: 12px;
    border-radius: 14px;
}
</style>
