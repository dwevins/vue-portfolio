<template>
    <div class="project-modal">
        <div class="modal-blocker" v-on:click="closeProject"></div>
        <div class="modal-body">

            <p>{{project}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'project-modal',

        props: [
            'project',
        ],

        methods: {
            closeProject() {
                this.$emit('closeProject');
            },
        },
    };
</script>

<style lang="css">
    .project-modal {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100vh;
    }
    .modal-blocker {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.5);
    }

    .modal-body {
        z-index: 2;
        width: 70%;
        background-color: #fff;
    }
</style>
