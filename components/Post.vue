<template>
    <a :href="pdata.link">
        <v-card flat>
            <v-card-media
                contain
                height="auto"
                :src="require('../assets/img/post/'+ pdata.img)"
            >
            </v-card-media>
            <v-card-text>
                <h2>
                    {{pdata.title}}
                </h2>
                {{pdata.discript}}
            </v-card-text>
        </v-card>
    </a>
</template>

<script>
export default {
  props: ['pdata'],
}
</script>

<style>

</style>
