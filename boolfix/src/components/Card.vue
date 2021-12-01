<template>
<section>
        <div v-if="image != null || image != undefined">
            <img :src="`https://image.tmdb.org/t/p/w185/${image}`">
        </div>
        <div v-else>
            Image not found
        </div>
        <div>
            {{ title }}
        </div>
        <div>
            {{ subTitle }}
        </div>
        <div class="language">
            <img v-if="getFlags" :src="require(`@/assets/${text}.png`)">
            <span v-else> {{ text }}</span>
        </div>

        <div>
            {{ number }}
        </div>
  </section>
</template>

<script>
export default {
      props: {
        image: String,
        title: String,
        subTitle: String,
        text: String,
        number: Number,
    },
     computed: {
        getFlags() {
            return this.languageimg.includes(this.text)
        }
    },
    data() {
		return {
			languageimg: ['it', 'en'],
		};
	},

}
</script>

<style scoped lang="scss">
    .language img{
        width: 185px;
    }
</style>