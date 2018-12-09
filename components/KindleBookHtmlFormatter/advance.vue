<template lang="pug">
  v-card
    v-toolbar(
      flat
    )
      v-toolbar-title Advance
      v-spacer
      v-btn(
        icon
        @click="isVisible = !isVisible"
      )
        v-icon arrow_drop_down
    v-container(
      v-show="isVisible"
    )
      v-text-field(
        label="publisher"
      )
      v-text-field(
        label="subject"
      )
      v-text-field(
        label="date"
      )
      v-text-field(
        label="description"
      )
</template>

<script>
export default {
  data() {
    return {
      isVisible: false
    }
  }
}
</script>

<style>

</style>
