<template>
    <nav class="nav-box">
        <div class="nav-box-inner1">
            <img src="../assets/Netflix-logo.png" alt="Netflix-logo">
            <ul>
                <li>Home</li>
                <li>Serie TV</li>
                <li>Film</li>
                <li>Originali</li>
                <li>Aggiunti di recente</li>
                <li>La mia lista</li>
            </ul>
        </div>
        <div class="nav-box-inner2">
            <form action="">
                <input type="text">
            </form>
            <button>CERCA</button>
            <div>BAMBINI</div>
        </div>
    </nav>
</template>

<script>



export default {
  name: "Header",
  components: {
    
  },

};
</script>

<style lang="scss" scoped>

    .nav-box {
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 80px;

        .nav-box-inner1{
            display: flex;
            align-items: center;
            justify-content: center;

            img {
                width: 100px;
            }

            ul {
                display: flex;
                align-items: center;
                justify-content: center;
                list-style: none;

                li {
                    padding-right: 12px;
                    color: white;
                }
            }
        }

        .nav-box-inner2 {
            display: flex;
            align-items: center;
            justify-content: center;
        }
    }

</style>
