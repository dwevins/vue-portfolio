<template>
    <div class="project" v-on:click="openProject">
        <p>{{ project.name }}</p>
    </div>
</template>

<script>
    export default {
        name: 'project',

        props: [
            'project',
            'index',
        ],

        methods: {
            openProject() {
                this.$emit('openProject', this.index);
            },
        },
    };
</script>

<style lang="css">
    .project {
        width: 20%;
        border: 1px solid black;
    }
</style>
