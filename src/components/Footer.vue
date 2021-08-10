<template>
    <footer>

        <a class="socialLink" v-for="(socialLink, index) in socialLinks" :key="index" :href="socialLink.link" target="_blank">
            <img :alt="socialLink.label" :title="socialLink.label" :src="socialLink.icon" >
        </a>

    </footer>
</template>

<script>
import api from '@/services/api.js'

export default {
    name:'Footer',
    data () {
        return {
            socialLinks: [],
            parsedObj: ""
        }
    },
    methods: {
        getLinks: function () {
            api.get('/social-links.json').then(response => {
                this.socialLinks = response.data
            })
        }
    },
    mounted (){
        this.getLinks()
    }
}
</script>

<style scoped>

    .socialLink {
        margin: 0 10px;
        border: 1px solid var(--color-text-light);
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50px;
        width: 40px;
        height: 40px;
    }

    footer {
        height: 60px;
        width: 100%;
        background-color: var(--color-background-nav);
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .socialLink img {
        width: 20px;
    }
</style>