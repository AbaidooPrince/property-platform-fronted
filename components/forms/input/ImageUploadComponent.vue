<template>
    <div>
        <b-card :class="$style.placeholderWrapper" :img-src="image">
                <b-button :class="$style.uploadButton" size="lg" variant="primary" @click="uploadFile">Upload</b-button>
            <input id="upload" type="file" hidden accept="image/*" :value="file" @change="getFile" />
        </b-card>
    </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
// import {ImageUploadProps} from './Input.types'

export default defineComponent({
    name: 'ImageUploadComponent',
})
</script>
<script lang="ts" setup>
let image = ''
const file = ref(null)
const uploadFile = () => {
    document.getElementById('upload')?.click()
}

const getFile = (e) => {
    const file  = e.target.value
    image = e.target.value
    console.log(e)

}
const props = defineProps<{
    src: string
    state: true | false 
}>()
</script>
<style module scoped>
.placeholderWrapper {
    display: flex;
    height: 250px;
    /* justify-content: center; */
    align-items: center;
    border: 0.25rem dashed var(--grey);
    /* border-style: dashed; */
}

.uploadButton {
    margin: auto;
}

</style>