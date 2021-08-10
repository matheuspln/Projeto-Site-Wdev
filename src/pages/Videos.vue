<template>
    <main>
        <h1>Videos</h1>
        <section class="container">
            <div class="video" v-for="(video, index) in videos" :key="index">
                <a :href="video.link" class="video" target="_blank">
                    <img :src="video.thumb" :ref="video.title" :title="video.title">
                    <p>{{video.title}}</p>
                </a>
            </div>
        </section>     
    </main>
</template>

<script>

import api from '@/services/api.js'

export default {
    name: 'Videos',
    data() {
        return {
            videos: []
        }
    },
    mounted() {
        api.get('/videos.json').then(response => {
            this.videos = response.data
        })
    }
}
</script>

<style scoped>
    main {
        flex-direction: column;
        align-items: center;
    }

    a img{
        width: 100%;
    }

    a p {
        text-align: center;
        color: var(--color-text-dark);
        font-weight: bold;
        font-size: 15px;
    }

    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .video {
        width: 80%;
        margin-bottom: 30px;
    }

    @media (min-width: 700px) {
        .container {
            flex-direction: row;
            align-items: flex-start;
            flex-wrap: wrap;
        }

        .video {
            width: 300px;
            margin-right: 20px;
        }
    }
</style>