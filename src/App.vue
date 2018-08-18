<template>
    <div id="app">
        <button @click="switchStyle(1)">Yellow</button>
        <button @click="switchStyle(2)">Orange</button>
    </div>
</template>

<script>
    export default {
        name: 'app',
        data() {
            return {
                msg: 'Welcome to Your Vue.js App'
            }
        },
        methods: {
            switchStyle(index) {
                let lastStyle = document.head.querySelector('style');
                lastStyle && document.head.removeChild(lastStyle);
                document.querySelector('#themeLink').href = `dist/style${index}.css`;
                localStorage.setItem('DISPLAY_STYLE', index);
            }
        }
    }
</script>

<style lang="scss">
</style>
