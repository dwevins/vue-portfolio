<template>
    <div id="app">
        <project v-for="project in projectList"></project>
        <project-modal></project-modal>
    </div>
</template>

<script>
    import Project from './components/Project';
    import ProjectModal from './components/ProjectModal';
    import ProjectList from './projects';

    export default {
        name: 'app',

        components: {
            Project,
            ProjectModal,
        },

        data() {
            return {
                projectList: ProjectList.projects,
                currentProject: null,
            };
        },

        methods: {
            openProject(id) {
                this.currentProject = this.projectList[id];
            },
        },
    };
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
