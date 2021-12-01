<template>
<section>
    <div>
            <img :src="`https://image.tmdb.org/t/p/w185/${image}`">
       </div>
       <div>
           {{ title }}
       </div>
       <div>
           {{ subTitle }}
       </div>
       <div>
           <img v-if="languageimg" :src="require(`../assets/${languageimg}.png`)">
           <span v-else> {{ original_language }}</span>
       </div>
       
       <div>
           {{ number }}
       </div>
  </section>
</template>

<script>
export default {

}
</script>

<style>

</style>