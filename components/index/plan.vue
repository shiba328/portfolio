<template lang="pug">
    div(class="mb-5")
        h1 Plan / Prototype
        v-layout(row wrap)
            v-flex(
                xs12 sm6 md3
                v-for="p in Plans"
                :key="p.id"
            )
                v-card(flat)
                v-img(
                    v-if="p.img"
                    :src="require('../../assets/img/post/' + p.img)"
                    aspect-ratio="1.9"
                ) 
                    v-chip( small outline color="red") {{p.type}} 
                v-card-text
                    h3(class="mb-0") {{p.title}}
                    div 
                    div
                    v-chip( v-for="c in p.genre" :key="c" small) {{c}}
                    div
                    v-chip( v-for="s in p.skills" :key="s" small label outline) {{s}} 
    
</template>

<script>
export default {
  computed: {
      Plans:() => [
        {
          id:1,
          type:"prototype/BtoC",
          img: 'cagamii.png',
          title:"スマートミラー用WEBサービス",
          skills:["iOS","firebase","vue",],
          genre:["ヘルスケア","美容"],
          discript:""
        },{
          id:2,
          type:"Plan/BtoC",
          img: 'armap.png',
          title:"ARマーカー小規模Mapシステム",
          skills:["iOS","firebase","vue",],
          genre:["位置情報","AR","iBeacon"]
        },{
          id:3,
          type:"Plan/BtoC",
          img: 'noimage.png',
          title:"スーパーマーケット向けサイネージシステム",
          skills:["raspberryPie","firebase","vue","wordpress"],
          genre:["デジタルサイネージ","レシピ"]
        },{
          id:4,
          type:"prototype/BtoBtoC",
          img: 'noimage.png',
          title:"イベント会場向け認証システム",
          skills:["firebase","vue","wordpress"],
          genre:["デジタルサイネージ","QR"]
        },{
          id:5,
          img: 'noimage.png',
          type:"prototype/BtoC",
          title:"わからないボタン",
          skills:["firebase","vue"],
          genre:["教育"]
        },{
          id:6,
          img: 'noimage.png',
          type: 'Plan/BtoB',
          title: "コードレビューメンター",
          skills:["firebase","vue"],
          genre:["教育"]
        }
      ]
  },
}
</script>

<style>

</style>
