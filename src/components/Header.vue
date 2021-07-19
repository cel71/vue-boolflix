<template>
    <nav class="nav-box">
        <div class="nav-box-inner1">
            <img src="../assets/Netflix-logo.png" alt="Netflix-logo">
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#"><span class="other-color">Serie TV</span></a></li>
                <li><a href="#"><span class="other-color">Film</span></a></li>
                <li><a href="#"><span class="other-color">Originali</span></a></li>
                <li><a href="#"><span class="other-color">Aggiunti di recente</span></a></li>
                <li><a href="#"><span class="other-color">La mia lista</span></a></li>
            </ul>
        </div>
        <div class="nav-box-inner2">
            <form action="">
                <input type="text" placeholder="Search" v-model="searchFilm">
                <i class="fas fa-search" @click="$emit('search', searchFilm)"></i>
            </form>
            <button @click="$emit('search', searchFilm)">CERCA</button>
            <div class="categoria">BAMBINI</div>
            <i class="fas fa-bell"></i>
            <i class="far fa-smile"></i>
            <i class="fas fa-sort-down"></i>
        </div>
    </nav>
</template>

<script>



export default {
  name: "Header",
  components: {
    
  },
  data: function () {
    return {
        searchFilm: ""
    }
  }

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
            padding-left: 15px;

            img {
                width: 100px;
                padding-bottom: 12px;
                cursor: pointer;
            }

            ul {
                display: flex;
                align-items: center;
                justify-content: center;
                list-style: none;

                li {
                    padding-right: 12px;

                    a {
                        text-decoration: none;
                        color: white;

                        .other-color {
                            color: rgb(149, 149, 149);
                        }
                    }
                }
            }
        }

        .nav-box-inner2 {
            display: flex;
            align-items: center;
            justify-content: center;
            padding-right: 15px;

            form {
                width: 250px;
                height: 40px;
                display: flex;
                align-items: center;
                justify-content: center;

                input {
                    margin-right: 15px;
                }

                i {
                    color: white;
                    font-size: 20px;
                    cursor: pointer;
                }
            }

            button {
                border: none;
                background-color: red;
                color: white;
                font-weight: bold;
                border-radius: 5px;
                margin-right: 15px;
            }

            .categoria {
                color: white;
                font-size: 15px;
                margin-right: 15px;
                cursor: pointer;
            }

            i {
                color: white;
                font-size: 20px;
                cursor: pointer;
                margin-right: 15px;
            }

            .fa-smile {
                font-size: 30px;
            }

            .fa-sort-down {
                padding-bottom: 5px;
            }
        }
    }

</style>
