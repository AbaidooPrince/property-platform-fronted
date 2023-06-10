<template>
    <div>
        <b-form @submit.prevent="handleFormSubmission">
        <image-upload-component :state="true" src="sd"></image-upload-component>
        <text-input-component id="name" v-model="form.name" label="Property Name" type="text" :state="state" />
        <items-dropdown-component></items-dropdown-component>
        <b-button variant="primary">Add Home</b-button>

        </b-form>
    </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import ImageUploadComponent from '../input/ImageUploadComponent.vue'
import ItemsDropdownComponent from '../input/ItemsDropdownComponent.vue'
import TextInputComponent from '../input/TextInputComponent.vue'
import { agents } from '~/store/mock'

export default defineComponent({
    components: {
        TextInputComponent,
        ImageUploadComponent,
        ItemsDropdownComponent
    },
    setup() {
        const selectedAgent = ref('')
        const state = ref(null)
        const form = {
            name: '',
            image: ''
        }

        const handleFormSubmission = () => {
            console.log(form)
        }
        return {
            form, handleFormSubmission, state, agents, selectedAgent
        }
        
    },
})
</script>