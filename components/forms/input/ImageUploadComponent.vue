<template>
    <div>
        <b-card>
            {{ props.src }}
        </b-card>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
// import {ImageUploadProps} from './Input.types'

export default defineComponent({
    name: 'ImageUploadComponent'
})
</script>
<script lang="ts" setup>
const props = defineProps<{
    src: string
    state: true | false 
}>()
</script>