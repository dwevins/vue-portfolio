<template>
    <div id="app">
        <div class="projects-container">
            <project
                v-for="(project, index) in projectList"
                v-bind:project="project"
                v-bind:index="index"
                v-bind:key="index"
                v-on:openProject="openProject">
            </project>
        </div>
        <project-modal
            v-if="currentProject"
            v-bind:project="currentProject"
            v-on:closeProject="closeProject">
        </project-modal>
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
            openProject(index) {
                this.currentProject = this.projectList[index];
            },

            closeProject() {
                this.currentProject = null;
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

    .projects-container {
        display: flex;
        justify-content: space-between;
        margin: 0 1rem;
        max-width: 200rem;
    }
</style>
