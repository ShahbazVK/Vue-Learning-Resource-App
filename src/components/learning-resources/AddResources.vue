<template>
<base-card>
    <form @submit.prevent="submitData()">
        <div>
            Title: <input id="title" type="text" ref="titleinput">
        </div>
        <br>
        <div>
            Description: <textarea name="description" id="description" cols="20" rows="3" ref="descinput"></textarea>
        </div>
        <br>
        <div>
            Link: <input id="link" type="text" ref="linkinput">
        </div>
        <br>

        <div>
            <base-button type="submit">Add Resource</base-button>
        </div>
    </form>
</base-card>
</template>

<script>
import BaseCard from '../UI/BaseCard.vue'
export default {
    components: {
        BaseCard
    },
    inject: ['addResource'],
    methods: {
        submitData() {
            const enteredTitle = this.$refs.titleinput.value
            const enteredDesc = this.$refs.descinput.value
            const enteredLink = this.$refs.linkinput.value
            // console.log(enteredTitle, enteredDesc, enteredLink)

            if (enteredTitle.trim() === '' || enteredDesc.trim() === '' || enteredLink.trim() === '') {
                alert("Fill all the fields")
            } else this.addResource(enteredTitle, enteredDesc, enteredLink)
        }

    }

}
</script>

<style>

</style>
