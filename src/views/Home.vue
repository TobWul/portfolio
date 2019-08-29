<template>
    <div class="home container preserve-scroll">
        <h2>
            Interaction design student, self-taught
            <br />developer and hobby photographer
        </h2>
        <section id="projects">
            <ul>
                <li
                    v-for="(project, index) in projects"
                    :key="index"
                    @mouseover="selectedProject = project"
                >
                    <router-link :to="project.link" class="project-thumbnail">
                        <img :src="project.image" alt />
                        <div class="text">
                            <h4 class="caps">{{ project.title }}</h4>
                            <p>{{ project.role }}</p>
                        </div>
                    </router-link>
                </li>
            </ul>
        </section>
    </div>
</template>

<script>
export default {
    name: 'home',
    components: {},
    data: function() {
        let projects = [
            {
                index: 0,
                title: 'Sanke – Gathering edible plants in oslo',
                role: 'UX, UI and frontend developer',
                link: '/sanke',
                image: require('../assets/sanke/SankeFront.png'),
            },
            {
                index: 1,
                title: 'Sentif – Excercise for wheelchair users',
                role: 'UX, UI',
                link: '/sentif',
                image: require('../assets/sentif/DoubleDiamond.png'),
            },
            {
                index: 2,
                title: 'Industrielldesign.no – Student website',
                role: 'UX, UI, frontend- and backend-developer',
                link: '/sentif',
                image: require('../assets/makerbox/Guide_home.png'),
            },
            {
                index: 3,
                title: 'Hoopit – New economics dashboard',
                role: 'UX, UI, frontend-developer',
                link: '/hoopit',
                image: require('../assets/makerbox/Guide_home.png'),
            },
            {
                index: 4,
                title: 'Makerbox – How to teach problem solving?',
                role: 'UI and frontend developer',
                link: '/sentif',
                image: require('../assets/makerbox/Guide_home.png'),
            },
        ];
        return {
            projects: projects,
            selectedProject: projects[0],
            stickyTop: 0,
        };
    },
    mounted: function() {
        this.stickyTop =
            Math.max(
                document.documentElement.clientHeight,
                window.innerHeight || 0
            ) /
                2 -
            document.getElementById('previewImage').offsetWidth / 2;
    },
    methods: {},
};
</script>

<style lang="scss" scoped>
.header {
    height: 40vh;
}
#projects {
    margin-top: 15%;
    ul {
        columns: 6 25vw;
        column-gap: 1rem;
        margin: 0;
        padding: 0;
        @media screen and (max-width: 900px) {
            column-width: 300px;
        }
        li {
            margin: 0;
            padding: 0;
            list-style-type: none;
        }
        .project-thumbnail {
            position: relative;
            background: #cccccc;
            color: white;
            margin: 0 1rem 1rem 0;
            display: inline-block;
            width: 100%;

            img {
                width: 100%;
                height: auto;
            }
            .text {
                color: $black;
                position: absolute;
                bottom: 2rem;
                left: 2rem;
            }
        }
    }
}
</style>
