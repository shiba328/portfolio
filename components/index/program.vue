<template lang="pug">
    div(class="mb-5")
      h1 Programming
      v-layout(row wrap)
        v-flex(
            xs12 sm6
            md4
            v-for="p in postData"
            :key="p.id"
          )
            v-card(flat :href="p.link")
                v-img(
                    :src="require('../../assets/img/post/'+ p.img)"
                    aspect-ratio="1.9"
                )
                v-card-text
                    h2 {{p.title}}
                    div {{p.discript}}
                    v-chip( v-for="s in p.skills" :key="s" small label outline) {{s}} 
</template>

<script>
export default {
  computed: {
      postData: () => [
        {
          id:1,
          link:'https://gs-shiba.sakura.ne.jp/lab02/',
          title: 'Flying Pizaa!',
          img: 'flyingPizaa.png',
          discript: 'HTML+JS+localstorageで簡易ゲーム。結果をlocalstorageに保存します',
          tag:['HTML/CSS','jQuery','LocalStorage'],
          period: '16h'
        },
        {
          id:2,
          link:'https://gs-shiba.sakura.ne.jp/lab03/',
          title: 'Janken Wars',
          img: 'JankenWars.png',
          discript: 'HTML+JS+ウェブカメラでじゃんけん。ウェブカメラで出し手の上に手をかざすとじゃんけんします',
          tag:['HTML/CSS','jQuery','canvas','webカメラ'],
          period: '24h'
        },{
          id:3,
          link:'https://gs-shiba.sakura.ne.jp/lab04/',
          title: 'iOSメモ帳クローン(マークダウン表示)',
          img: 'memo1.png',
          discript: 'iOSのメモをそのままJSで表現。マークダウン表示に変更できます',
          skills:['HTML/CSS','jQuery','LocalStorage','json'],
          period: '12h'
        },{
          id:4,
          link:'https://gs-shiba.sakura.ne.jp/lab05/',
          title: '四文字熟語を答えよう！',
          img: 'yonmoji.png',
          discript: '４文字熟語ドリル。空白に文字を入れて４文字熟語を答えよう',
          skills:['HTML/CSS','jQuery','json'],
          period: '8h'
        },{
          id:5,
          link:'https://gs-shiba.sakura.ne.jp/lab06/',
          title: 'OldMaid',
          img: 'oldmaid.png',
          discript: 'Firebaseを利用して、リアルタイムババ抜き対戦',
          skills:['HTML/CSS','jQuery','firebase','LocalStorage'],
          period: '38h'
        }
      ],
  },
}
</script>

<style>

</style>
