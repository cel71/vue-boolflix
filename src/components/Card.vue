<template>
    <div class="box-immagini">
        <img :src="Image">
        <div class="dati">
            {{title}}
            {{original_title}}
            {{original_language}}
            {{vote_average}}
        </div>
    </div>
</template>

<script>

export default {
  name: "Card",
  props: {
    Image: String,
    title: String,
    original_title: String,
    original_language: String,
    vote_average: Number,
  },
};
</script>

<style lang="scss" scoped>

    .box-immagini {
        text-align: center;
        color: white;

        img {
            width: 100%;
            cursor: pointer;
        }

    }

</style>
