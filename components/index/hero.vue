<template lang="pug">
    div(class="mb-5" style="text-align: center;" )
        h1 About Me
        h2 しば みつえ
        p(style="font-size: 150%;") Markup Engineer → Frontend Engineer
        v-layout(row wrap align-center)
        v-flex(xs8 offset-xs2)
            p(style="font-size: 120%; white-space:nowrap; ")
            | ３歳の子供がいるママエンジニアです。
            | 中規模なWEB系の会社で<wbr>マーケティング・制作チームで、<wbr>
            | Wordpressを利用した<wbr>WEB制作を担当していました。<wbr>
            | もっとシステムに寄った<wbr>仕事がしたいため、<wbr>転職活動しています。<wbr>
            | 現在は受託でWEB制作を行なっています。<wbr>
            | 一人で動いてるので、<wbr>一緒にレベル上げしてくれる<wbr>仲間と師匠が欲しいです。<wbr>
            div
                v-btn(href="https://qiita.com/shiba_mitue" color="#4fc700" dark) Qitta
                v-btn(href="https://twitter.com/shiba_328" color="#1da1f2" dark) twitter
                div(class="mt-5")
        v-btn(href="https://m.me/mitue.okamoto" target="_blank" dark outline) \ 1ヶ月週3〜!社会人インターン先募集中！無償・有償 応相談 /
        div(mt-3) このポートフォリオはVue(Next.js)+TravisCI+GitHubPageで作成しています。
</template>

<script>
export default {

}
</script>

<style>

</style>
