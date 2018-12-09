<template lang="pug">
  v-app
    v-container
      h1 Kindle Book HTML Formatter
      h2 meta
      setting
      advance
      h2 index generator
      indexgen
</template>

<script>
import setting from '~/components/KindleBookHtmlFormatter/setting'
import advance from '~/components/KindleBookHtmlFormatter/advance'
import indexgen from '~/components/KindleBookHtmlFormatter/indexgen'

export default {
  components: {
    setting,
    advance,
    indexgen
  },
  data() {
    return {
    }
  }
}
</script>

<style>

</style>
