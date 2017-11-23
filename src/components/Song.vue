<template>
    <div class="column">
        <div class="button is-large is-danger" :class="colours" @click="play">
            <h1>{{ song.title }}</h1>
        </div>
    </div>
</template>

<script>
export default {
    props: ['song'],
    computed: {
        colours() {
            if (this.song.type !== 'excessive') {
                return 'is-outlined';
            }
            return null;
        },
    },
    methods: {
        play(){
            this.$emit('play', this.song.id);
        },
    },
};
</script>

<style scoped>
.button {
    width: 100%;
    height: 5em;
}
</style>
