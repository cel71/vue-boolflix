<template>
    <div class="box-immagini">
        <div class="box-immagini-inner">
            <div class="immagini">
                <img :src="'https://image.tmdb.org/t/p/w500/' + poster_path" :alt="`${title}`"/>
                <div class="dati">
                    <div class="title">{{title.toUpperCase()}}</div>
                    <div class="original-title">ORIGINAL TITLE: {{original_title}}</div>
                    <div class="bandiera">
                        <div class="original_language">LANGUAGE: {{original_language}}</div>
                        <img :src="bandiere(original_language)" alt="bandiere"/>
                    </div>
                    <div class="line"></div>
                    <div class="star">
                        <i v-for="x in 5" :key="x" class="fa-star" :class="x <= finalVote ? 'fas' : 'far'"></i>
                    </div>
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
  data: function () {
    return {
        finalVote: Math.round (this.vote_average / 2),
    }
  },
  methods : {
    bandiere (originalLanguage) {
        return require ("../assets/" + originalLanguage + ".svg");
    }
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
                    padding-top: 80px;
                    bottom: 0;
                    left: 0;
                    right: 0;
                    height: 100%;
                    width: 100%;
                    opacity: 0;
                    background-color: rgba(0, 0, 0, 0.7);

                    .bandiera {
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        
                        img {
                            width: 45px;
                            margin: 0;
                            padding-bottom: 18px;
                        }
                    }

                    .line {
                        width: 200px;
                        height: 2px;
                        background-color: white;
                        margin: 15px auto;
                    }

                    .star {
                        padding-top: 18px;
                        
                        .fa-star {
                            color: gold;
                            font-size: 20px;
                        }
                    }
                }                
            }

            .immagini:hover .dati {
                cursor: pointer;
                opacity: 1;
            }

            .title {
                color: gold;
            }

            .title, .original-title, .original_language, .vote_average {
                padding: 0 12px 20px;
                font-size: 16px;
            }
        }
    }

</style>
