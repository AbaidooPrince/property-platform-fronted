<template>
  <div>
    <b-button
      id="toggle-modal"
      v-b-modal.toggle-modal
      variant="primary"
      size="sm"
      class="btn btn-primary my-2 my-sm-0"
      >{{ label }}</b-button
    >
    <b-modal
      id="toggle-modal"
      ref="toggle-modal"
      :hide-footer="hideFooter"
      :title="title"
    >
      <div class="">
        <slot name="content"></slot>
      </div>
    </b-modal>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    label: {
      type: String,
      default: '',
    },
    hideFooter: {
        type: Boolean
    },
    title: {
        type: String,
        default: ''
    }
  },
  setup(props) {
    return props
  },
})
</script>