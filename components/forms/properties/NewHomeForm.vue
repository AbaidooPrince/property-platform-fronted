<template>
    <div>
        <b-form @submit.prevent="handleFormSubmission">
        <text-input-component id="name" v-model="form.name" label="Property Name" type="text" :state="state" />
        <b-button class="" variant="primary">Add Home</b-button>

        </b-form>
    </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import TextInputComponent from '../input/TextInputComponent.vue'

export default defineComponent({
    components: {
        TextInputComponent
    },
    setup() {
        const state = ref(null)
        const form = {
            name: '',
            image: ''
        }

        const handleFormSubmission = () => {
            console.log(form)
        }
        return {
            form, handleFormSubmission, state
        }
        
    },
})
</script>