<template>
<section>
        <div class="img-movie">
            <div class="img-cover" v-if="image != null || image != undefined">
                <img :src="`https://image.tmdb.org/t/p/w1280${image}`">
            </div>
            <div class="not-found-image" v-else>
                <img src="@/assets/not-found-image-15383864787lu.jpg" alt="">
            </div>
        </div>
        <div class="hover-info">
            <div>
                <b>Titolo</b>: {{ title }}
            </div>
            <div>
                <b>Sottotitolo</b>: {{ subTitle }}
            </div>
            <div class="language">
                <b>Lingua:</b>
                <img v-if="getFlags" :src="require(`@/assets/${text}.png`)">
                <span v-else> {{ text }}</span>
            </div>

            <div class="vote">
                <h3>Voto:</h3>
               <span>
                   <i v-for="(number, i) in VoteStars" :key="`vote-${i}`" class="fas fa-star"></i>

                    <i v-for="(number, i) in 5 - VoteStars" :key="`vote-2-${i}`" class="far fa-star"></i>
               </span>
            </div>
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
        },
        VoteStars() {
            return Math.ceil( this.number / 2)
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
    .not-found-image img{
        width: 185px;
    }
    .language b{
        padding: 0 10px;
    }
    
    img{
        width: 30px;
    }

    .img-cover img{
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        border-radius: 10px;
    }
    .hover-info {
        position: absolute;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: column;
        justify-content: end;
        opacity: 0;
        cursor: pointer;
        transition: opacity .5s;
        background: rgba(0,0,0,.8);
        padding-bottom: 3rem;
        width: 100%;
        height: 100%;
        color: #fff;
        box-shadow: 0 0 20px rgba(0,0,0,.5) inset;
        border-radius: 10px;
        z-index: 1;

        &:hover {
            opacity: 1;
        }}

        i{
            color: yellow;
        }
        
        div{
            padding-bottom: 10px;
        }

        .vote{
            display: flex;
            align-items: center;
            justify-content: center;

            h3{
                font-size: 18px;
                margin-bottom: 0;
                padding: 0 5px;
            }
        }
</style>