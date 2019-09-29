<template>
    <div class="home container preserve-scroll">
        <section id="projects">
            <router-link
                :to="project.link"
                class="project"
                v-for="(project, index) in projects"
                :key="index"
            >
                <div class="face front">
                    <img :src="project.image" alt />
                </div>
                <div class="face right"></div>
                <div class="face top"></div>
                <div class="face shadow"></div>
            </router-link>
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
.project {
    $project-animation-duration: 400ms;
    position: relative;
    width: 200px;
    height: 200px;
    display: inline-block;
    transform-origin: bottom;
    @for $i from 0 through 10 {
        &:nth-child(#{$i + 1}) {
            top: $i * 75px;
        }
    }
    &:hover {
        .face.front,
        .face.right {
            height: 250px;
        }
        .face.top,
        .face.front,
        .face.right {
            top: -50px;
        }
        .face.shadow {
            transform: rotate(20deg) skewX(-50deg) skewY(0deg) scaleY(1.2)
                translate(231px, 70px);
        }
    }
    .face {
        position: absolute;
        top: 0;
        left: 0;
        width: 180px;
        height: 200px;
        background: hsl(0, 0, 98);
        margin: 0 1rem 1rem 0;
        transition: height $project-animation-duration ease-in-out,
            top $project-animation-duration ease-in-out;

        &.front {
            transform: rotate(20deg) skewX(20deg);
            img {
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        }
        &.right {
            transform: rotate(-20deg) skewX(-20deg) skewY(0deg)
                translateX(185.5px) translateY(87.2px);
            width: 8px;
            background: hsl(0, 0, 90);
        }
        &.top {
            transform: rotate(-20deg) skewX(50deg) skewY(0deg)
                translateY(-70.6px) translateX(205.4px) scaleY(0.579);
            width: 8px;
            background: hsl(0, 0, 95);
        }
        &.shadow {
            transform: rotate(20deg) skewX(-50deg) skewY(0deg) scaleY(0.87)
                translate(228px, 115px);
            background: rgba(0, 0, 0, 0.4);
            height: 100px;
            z-index: -1;
            transition: transform $project-animation-duration ease-in-out;
        }
    }
}
</style>
