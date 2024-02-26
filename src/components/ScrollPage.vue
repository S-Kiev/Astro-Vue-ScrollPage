<template>
    <div class="slider" ref="slider">
        <div class="navbar">
            <a href="#" @click="moveScroll(1)">INICIO</a>
            <a href="#" @click="moveScroll(2)">DOCUMENTACION</a>
            <a href="#" @click="moveScroll(3)">CONTACTO</a>
            <a href="#" @click="moveScroll(4)">PROYECTOS</a>
        </div>
        <div class="content_page">
            <h2>INICIO</h2>
        </div>
          
        <div class="content_page">
            <h2>DOCUMENTACION</h2>
        </div>
        <div class="content_page">
            <h2>CONTACTO</h2>
        </div>
        <div class="content_page">
            <h2>PROYECTOS</h2>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                slider : null,
                height : null
            }
        },

        mounted(){
            this.slider = this.$refs.slider;
            this.height = this.slider.offsetHeight;
        },

        methods: {
            moveScroll (n) {
                n = n - 1;
                this.slider.scrollTo ({
                    top: this.height * n,
                    behavior: 'smooth'
                });
            }
        }
    }
</script>

<style>
    html, body {
        height: 100vh;
        margin: 0;
        padding: 0;
        font-family: Arial, Helvetica, sans-serif;
    }

    .slider {
        position: relative;
        height: 100vh;
        overflow: scroll;
    }

    .content_page {
        width: 100%;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: white;
        color: black;
        font-size: 3rem;
        display: flex;
    }

    .navbar {
        position: fixed;
        top: 0;
        width: 100%;
        height: 60px;
        background-color: black;
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .navbar a {
        color: white;
        text-decoration: none;
        font-size: 1.5rem;
        display: block;
        text-align: center;
        float: left;
        padding: 14px 16px;
    }
    
    .navbar a:hover {
        background-color: #ddd;
        color: black;
    }
</style>