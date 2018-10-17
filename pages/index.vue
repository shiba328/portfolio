<template lang="pug">
  v-container(grid-list-lg fluid)
    v-layout(row wrap)
      v-flex(xs12 sm8)
        bubble
        hero
        skill
        program
        plan
        merit
        price
        contact
      v-flex(xs12 sm4)
        tweet
</template>

<script>
import tweet from '~/components/index/tweet.vue'
import skill from '~/components/index/skill.vue'
import hero from '~/components/index/hero.vue'
import program from '~/components/index/program.vue'
import plan from '~/components/index/plan.vue'
import merit from '~/components/index/merit.vue'
import contact from '~/components/index/contact.vue'
import price from '~/components/index/price.vue'
import bubble from '~/components/index/bubble.vue'

export default {
  components: {
    tweet,
    skill,
    hero,
    program,
    plan,
    merit,
    price,
    contact,
    bubble
  },
  data() {
    return {
      toggle: 1,
      scrollY: 0,
      time: 2000
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.scrollY = window.scrollY
      console.log(this.scrollY)
    }
  }
}
</script>
<style>
h1 {
  font-size: 280%;
  font-weight: normal;
  text-align: center;
}
h2 {
  font-size: 200%;
  font-weight: normal;
}
body {
  font-family: Source Sans Pro, -apple-system, BlinkMacSystemFont, Segoe UI,
    Roboto, Helvetica Neue, Arial, sans-serif;
}
</style>

