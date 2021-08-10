<template>
    <main>
        <h1>Sobre</h1>
        <div class="container">
            <p v-html="about"></p>
        </div>
    </main>    
</template>

<script>
import api from '@/services/api.js'
export default {
    name: 'Sobre',
    data () {
        return {
            about: ""
        }
    },
    mounted () {
        api.get('/about.json').then(response => {
            this.about = response.data.about
        })
    }
}
</script>

<style scoped>
    main {
        flex-direction: column;
        align-items: center;
    }

    p {
        margin-bottom: 20px;
        color: var(--color-text-dark)
    }
</style>