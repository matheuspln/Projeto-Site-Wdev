<template>
    <main>
        <div id="text-top"><p>Vídeo novo toda <b>Quinta</b> às <b>20h</b> </p></div>
        <a href="http://youtube.com/wdevoficial" target="blank"><img alt="increva-se" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/subscribe.svg
    " id="subscribe"></a>
        <div id="text-bottom"><p>youtube.com/wdevoficial</p></div>
    </main>
</template>

<script>
export default {
    name: 'Home'
}
</script>

<style scoped>
main {
    background-color: var(--color-background-home);
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

#text-top {
    color: var(--color-text-light);
    font-size: 22px;
}

#text-bottom {
    color: var(--color-text-light);
    font-size: 18px;
}

#subscribe {
    margin: 20px 0;
}
</style>