<template>
  <VDialog
    :value="isShow"
    class="rounded-lg"
    @click:outside="onClose"
    @keydown.esc="onClose"
    @input="onClose"
  >
    <VCard class="rounded-lg pa-4">
      <VCardTitle class="pa-0 flex-nowrap align-baseline justify-space-between">
        <span class="tt-text-title-2"> диалог </span>
      </VCardTitle>

      <slot />
    </VCard>
  </VDialog>
</template>
<script>
import Vue from "vue";
export default Vue.extend({
  name: "Dialog",
  props: {
    isShow: {
      type: Boolean,
      default: false,
    },
  },
  model: {
    prop: "isShow",
    event: "close",
  },
  methods: {
    onClose(event) {
      this.$emit("close", event.target.value);
    },
  },
});
</script>

