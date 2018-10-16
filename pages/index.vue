<template lang="pug">
  v-container(grid-list-lg fluid)
    hero
    skill
    program
    plan
    merit
    div(style="text-align: center;" )
      h1 Contact ME
      p(style="font-size: 120%;width:70%;")
      v-btn(href="https://m.me/mitue.okamoto" target="_blank" ) Messageを送信
</template>

<script>
import skill from '~/components/index/skill.vue'
import hero from '~/components/index/hero.vue'
import program from '~/components/index/program.vue'
import plan from '~/components/index/plan.vue'
import merit from '~/components/index/merit.vue'

export default {
  components: {
    skill,
    hero,
    program,
    plan,
    merit
  },
  data(){
    return{
    }
  },

}
</script>
<style>
h1{
  font-size: 280%;
  font-weight: normal;
  text-align: center
}
h2{
  font-size: 200%;
  font-weight: normal;
}
body{
      font-family: Source Sans Pro,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,sans-serif;
}
</style>

