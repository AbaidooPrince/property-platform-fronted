<template>
    <div>
    <b-form-group
      :id="`fieldset-${props.id}`"
      :description="props.description"
      :label="props.label"
      :label-for="`input-${props.id}`"
      :valid-feedback="props.validFeedback"
      :invalid-feedback="props.invalidFeedback"
      :state="props.state"
    >
      <b-form-input :id="`input-${props.id}`" v-model="value" :type="props.type" :state="props.state" trim></b-form-input>
    </b-form-group>
    </div>
</template>
<script lang="ts">
import { defineComponent , ref } from "vue"
// import { TextInputProps } from "./Input.types";
export default defineComponent({
    name: 'TextInputComponent'
})
</script>
<script lang="ts" setup>

const value = ref('')

const props = defineProps<{
    id?: string
    validFeedback?: string
    label: string
    description?: string
    invalidFeedback?: string
    type: string
    // value: {
    //     type: String,
    //     default: ''
    // },
    state: unknown
}>()
</script>
