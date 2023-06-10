<template>
  <div>
    <b-form-group label="Select agent">
    <b-form-select v-model="value" label-field="Placehoerl" class="mb-3">

<!-- These options will appear after the ones from 'options' prop -->
<b-form-select-option
  v-for="(item, l) in items"
  :key="l + '_item'"
  :value="item.id"
  >{{ item.name }}</b-form-select-option
>
</b-form-select>
    </b-form-group>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import { agents } from '~/store/mock'

type AgentProps = {
  id: string
  name: string
  image: string
  phone: string
  rank: string
}
export default defineComponent({
  setup() {
    const items: Array<AgentProps> = agents
    const value = ref('')

    return {
      items,
      value,
    }
  },
})
</script>
