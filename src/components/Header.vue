<template>
    <header>
        <nav class="container">
            <router-link to="/"><img alt="WDEV" id="logo" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg
    "></router-link>
            <img v-on:click="openMenu" alt="abrir menu" id="menu" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/menu.svg
    ">        
        </nav>

        <div v-on:click="closeMenu" id="menu-overlay" v-if="menuActive"></div>

        <div id="menu-items" :class="{active:menuActive}">
            <img alt="WDEV" id="menu-logo" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg
    ">
            <ul>
                <li v-on:click="closeMenu"><router-link to="/">Home</router-link></li>
                <li v-on:click="closeMenu"><router-link to="/videos">Vídeos</router-link></li>
                <li v-on:click="closeMenu"><router-link to="/sobre">Sobre</router-link></li>
                <li v-on:click="closeMenu"><router-link to="/contatos">Contatos</router-link></li>
            </ul>
        </div>
    </header>
</template>

<script>
export default {
    name:'Header',
    data () {
        return {
            menuActive: false
        }
    },
    methods: {
        openMenu: function (){
            this.menuActive = true;
        },
        closeMenu: function (){
            this.menuActive = false;
        }
    }
}
</script>

<style scoped>
header {
    width: 100%;
    background-color: var(--color-background-nav);
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 60px;
}

#logo {
    width: 130px;
}

#menu {
    width: 30px;
}

#menu-overlay {
    width: 40%;
    height: 100vh;
    background-color: var(--color-background-nav);
    position: fixed;
    top: 0;
    left: 0;
    opacity: 0.8;
}

#menu-items {
    width: 60%;
    height: 100vh;
    background-color: var(--color-background-nav);
    position: fixed;
    top: 0;
    right: 0;
    display: none;
    flex-direction: column; 
    align-items: center;  
}

#menu-items.active {
    display: flex;
}

#menu-logo {
    width: 110px;
    margin-top: 20px;
}

ul {
    list-style: none;
    text-align: center;
}

ul li {
    margin: 20px 0;
}

ul li a {
    color: var(--color-text-light);
}

@media (min-width: 700px) {
    #menu-logo,
    #menu-overlay,
    #menu {
        display: none;
    }

    #menu-items {
        display: flex;
        height: 60px;
        position: static;
        align-items: center;
        justify-content: center;
        width: auto;
    }

    ul {
        display: flex;
    }

    ul li {
        margin: 0;
        margin-right: 20px;
    }

    .container {
        width: 75%;
    }
}
</style>