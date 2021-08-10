<template>
    <main>
        <div class="container">
            <h1>Contatos</h1>
            <div class="contato" v-for="(contato, index) in contatos" :key="index">
                <p>{{contato.title}}</p>
                <a :href="contato.link" target="_blank">{{contato.label}}</a>
            </div>
        </div>
    </main>
</template>

<script>
import api from '@/services/api.js'
export default {
    name: 'Contatos',
    data (){
        return {
            contatos: []
        }
    },
    mounted(){
        api.get('/contacts.json').then(response =>{
            this.contatos = response.data
        })
    }
}
</script>

<style scoped> 
    .container {
        flex-direction: column;
    }

    main {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .contato {
        margin-bottom: 10px;
    }

    p {
        font-weight: 600;
    }

    a {
        color: var(--color-text-dark);
    }

</style>