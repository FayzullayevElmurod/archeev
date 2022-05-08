<template>
    <div class="header">
        <div class="container">
            <ul>
                <li class="logo">
                    <a href="#">
                        <img src="images\icons\Layer 2.svg" alt="">
                        <img src="images\Archeelogo.png" alt="">
                    </a>
                </li>
                <li class="navbar">
                    <ul>
                        <li v-for="(nav, index) in navbar" :key="index">
                            <a class="nav_item" :class="navbarTitle == nav.name ? 'active' : ''" @click="navClick(nav.name)" href="#">{{nav.name}}</a>
                        </li>
                    </ul>
                </li>
                <li>
                    <div class="lang">ENG</div>
                    <button>Contact</button>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'header',
    data() {
        return {
            navbar: [
                {name: 'Home'},
                {name: 'Project'},
                {name: 'Services'},
                {name: 'About'}
            ],
            navbarTitle: 'Home'
        };
    },

    mounted() {
        },

    methods: {
        navClick(title){
            this.navbarTitle = title;
            
        }        
    },
};
</script>

<style scoped>
.header{
    padding: 20px 0;
}
a{
    color: black;
    text-decoration: none;
}
*{
    margin: 0;
    padding: 0;
}
.container{
    width: 80%;
    margin: auto;
}
ul{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
ul li{
    list-style-type: none;
}
.logo img:not(:last-child){
    margin-right: 5px;
}
.navbar a{
    font-size: 14px;
    color: #2c2321;
    font-weight: 500;
    text-transform: uppercase;
    transition: 0.5s ease all;
}
.active{
    border-bottom: 1px solid #2c2321;
}
.navbar ul li:not(:last-child){
    margin-right: 30px;
}
ul li:last-child{
    display: flex;
    align-items: center;
}
.lang{
    color: #2c2321;
    font-size: 14px;
    font-weight: 500;
}
ul li:last-child button{
    background: #d6680f;
    outline: none;
    border: none;
    border-radius: 6px;
    padding: 10px 30px;
    font-size: 16px;
    font-weight: 700;
    color: #fff;
    margin-left: 30px;
}


</style>