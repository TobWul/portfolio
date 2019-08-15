<template>
    <div class="home container preserve-scroll">
        <section class="header">
            <h1>Tobias Wulvik</h1>
        </section>
        <section id="projects">
            <ul>
                <li
                    v-for="(project, index) in projects"
                    :key="index"
                    @mouseover="selectedProject = project"
                >
                    <router-link
                        :to="project.link"
                        :class="{'selected': project.index === selectedProject.index}"
                    >
                        <h4 class="caps">{{ project.title }}</h4>
                        <p>{{ project.role }}</p>
                    </router-link>
                </li>
            </ul>
            <div class="sticky-container" data-v-sticky-container>
                <div
                    class="preview-image sticky"
                    v-sticky
                    sticky-offset="{top: stickyTop, bottom: stickyTop}"
                >
                    <img
                        id="previewImage"
                        :src="selectedProject.image"
                        :alt="selectedProject.title"
                    />
                </div>
            </div>
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
                title: 'sanke – gathering edible plants in oslo',
                role: 'UX, UI and frontend developer',
                link: '/sanke',
                image: require('../assets/makerbox/Guide_home.png'),
            },
            {
                index: 1,
                title: 'sentif – excercise for wheelchair users',
                role: 'UX, UI',
                link: '/sentif',
                image: require('../assets/makerbox/Guide_home.png'),
            },
            {
                index: 2,
                title: 'industrielldesign.no – student website',
                role: 'UX, UI, frontend- and backend-developer',
                link: '/sentif',
                image: require('../assets/makerbox/Guide_home.png'),
            },
            {
                index: 3,
                title: 'makerbox – how to teach problem solving?',
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
.home {
}
.header {
    height: 40vh;
}
#projects {
    display: grid;
    grid-template-columns: 1fr 1fr;

    ul {
    }

    ul li {
        margin-bottom: 6rem;
        h4 {
            margin-bottom: 1rem;
        }
        a {
            text-decoration: none;
            color: $dark-gray;
            transition: color 200ms ease-in-out;
            will-change: color;

            &:hover,
            &.selected {
                color: $black;
            }
        }
    }
}
.preview-image {
    max-width: 100%;
    max-height: 60vh;

    // &.top-sticky {
    //     display: flex;
    //     align-items: center;
    //     position: fixed;
    //     top: 0;
    //     height: 100vh;
    // }

    img {
        max-width: 100%;
        max-height: 100%;
    }
}
</style>
