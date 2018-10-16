<template lang="pug">
    div(id="skillArea" class="mb-5")
      h1 Skill
      v-layout(row justify-center align-center text-xs-center)
        v-flex(xs5): h2 BackEnd
        v-flex(xs2): v-divider
        v-flex(xs5): h2 FrontEnd
      v-layout(row justify-center align-center text-xs-center)
        v-flex(xs5)
          v-layout(row justify-center align-center text-xs-center)
            v-flex(xs6)
              v-icon(color="red lighten-1") favorite
              div Like
            v-flex(xs6) 
              v-icon(color="amber lighten-1")  battery_charging_full
              div Power
        v-flex(xs2)
        v-flex(xs5)
          v-layout(row justify-center align-center text-xs-center)
            v-flex(xs6)
              v-icon(color="amber lighten-1") battery_charging_full
              div Power
            v-flex(xs6)
              v-icon(color="red lighten-1") favorite
              div() Like
      template(v-for="(skill,i) in Fskills")
        v-layout( :key="skill[0]" row justify-center align-center text-xs-center)
          v-flex(xs5)
            v-layout(row wrap justify-center align-center text-xs-center)
              v-flex(xs6 style="position: relative;")
                div(style="position: absolute;z-index: 2;color:#fff;margin:0 5px") {{ Bskills[i][2] }}%
                v-progress-linear(
                    color="red lighten-1"
                    height="20"
                    :value="Bskills[i][2]"
                    style="margin:0"
                )
              v-flex(xs6 style="position: relative;")
                  div(style="position: absolute;z-index: 2;color:#fff;margin:0 5px")  {{ Bskills[i][1] }}%
                  v-progress-linear(
                      color="amber lighten-1"
                      height="20"
                      :value="Bskills[i][1]"
                      style="margin:0"
                  )
              v-flex(xs12 text-xs-right style="padding-top:0;color:#ce792b"): small {{ Bskills[i][0] }}
          v-flex(xs2)
            i( class="fas" :class="[Nskills[i][1]]")
            div {{ Nskills[i][0] }}  
          v-flex(xs5)
            v-layout(row wrap justify-center align-center text-xs-center)
              v-flex(xs6)
                div(style="position: absolute;z-index: 2;color:#fff;margin:0 5px") {{skill[1]}}%
                v-progress-linear(
                    color="amber lighten-1"
                    height="20"
                    :value="skill[1]"
                    style="margin:0"
                  )
              v-flex(xs6)
                div(style="position: absolute;z-index: 2;color:#fff;margin:0 5px")  {{skill[2]}}%
                v-progress-linear(
                    color="red lighten-1"
                    height="20"
                    :value="skill[2]"
                    style="margin:0"
                  )
              v-flex(xs12　text-xs-left style="padding-top:0;color:#ce792b"): small {{ Fskills[i][0] }}    
    
</template>

<script>
export default {
  computed: {
      Nskills: () => [
        ["WordPress","fa-check-circle"],
        ["Vue(nuxt)","fa-check-circle"],
        ["Laravel","fa-check-circle"],
        ["Swift","fa-check-circle"],
      ],
      Fskills: () => [
        ["NoThema Full Customize",90,99],
        ["Vutyfiy/axsios/store/middleware",60,99],
        ["make website",40,50],
        ["Todo録音アプリ(※開発のみ)",30,10],
      ],
      Bskills:() => [
        ["MySQL/API/ACF",80,99],
        ["FirebaseRTDB/Store/Storage/Hosting",70,99],
        ["MySQL",20,20],
        ["UserDefault(*Realmは未経験)",10,10],
      ],
  },
}
</script>

<style>

</style>
