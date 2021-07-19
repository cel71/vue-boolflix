<template>
    <div class="box-immagini">
        <div class="box-immagini-inner">
            <div class="immagini">
                <img :src="'https://image.tmdb.org/t/p/w500/' + poster_path" :alt="`${title}`"/>
                <div class="dati">
                    <div class="title">TITLE: {{title}}</div>
                    <div class="original-title">ORIGINAL TITLE: {{original_title}}</div>
                    <div class="original_language">LANGUAGE: {{original_language}}</div>
                    <div class="vote_average">VOTE: {{vote_average}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: "Card",
  props: {
    poster_path: String,
    title: String,
    original_title: String,
    original_language: String,
    vote_average: Number,
  },
};
</script>

<style lang="scss" scoped>

    .box-immagini {
        color: white;

        .box-immagini-inner {

            .immagini {
                position: relative;

                img {
                    width: 100%;
                    margin-top: 30px;
                    display: block;
                }

                .dati {
                    text-align: center;
                    font-weight: bold;
                    position: absolute;
                    padding-top: 60px;
                    bottom: 0;
                    left: 0;
                    right: 0;
                    height: 100%;
                    width: 100%;
                    opacity: 0;
                    background-color: rgba(0, 0, 0, 0.7);
                }                
            }

            .immagini:hover .dati {
                cursor: pointer;
                opacity: 1;
            }

            .title, .original-title, .original_language, .vote_average {
                padding: 0 15px 12px;
                font-size: 18px;
            }
        }
    }

</style>
