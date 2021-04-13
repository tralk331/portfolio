<template>
    <div class="home-page">
        <div class="header">
                <img class="picture" src="../assets/logo.png">  
                <span class="name">Péter Szabó</span>
        </div>
        <div class="about">
            <h1>About me</h1>
            <span class="content">
                I am a software and web developer from Hungary. <br>
                It's my passion to create applications that others will use and enjoy. <br>
                Find out about my projects below.
            </span>
        </div>
        <div class="projects">
            <h1>Projects</h1>
            <div class="projects-grid">
                <project-widget v-for="project in projects" :key="project.id" v-bind="project"></project-widget>
            </div>
        </div>
    </div>
</template>

<script>
import ProjectWidget from '../components/ProjectWidget.vue'
export default {
    name: 'Home',
    components: {
        ProjectWidget
    },
    data() { 
        return {
            projects: [
                {
                    id: 0,
                    projectName: "Kalozgame-web",
                    description: 'A website with React front-end and PHP back-end.',
                    picturePath: "",
                    technologies: ["React", "PHP", "MySQL"]
                },
                {
                    id: 1,
                    projectName: "Kalozgame",
                    description: "A game I and some friends made as a school project",
                    picturePath: "",
                    technologies: ["C#", "Unity"]
                },
                {
                    id: 2,
                    projectName: "Novlio",
                    description: "A webapp for writers",
                    picturePath: "",
                    technologies: ["Angular", "Firebase"]
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    .home-page{
        height: 100%;
        background-color: rgb(219, 219, 219);
        h1 {
            font-size: 40px;
            font-family: 'Nunito', sans-serif;
        }
        .header {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-around;
            margin: auto;
            background-color: gray;
            padding: 2%;
            border-bottom: 1px solid black;
            .picture {
                display: block;
                max-height: 80%;
                height: auto;
                width: 50%;
                border: 1px solid black;
                border-radius: 50%;
            }
            .name{
                font-size: 45px;
                font-family: 'Rubik', sans-serif;
            }
        }
        .about {
            text-align: center;
            padding: 20px;
            .content {
                display: block;
                
                margin: auto;
                font-size: 25px;
                font-family: 'Rubik', sans-serif;
                letter-spacing: 0.8px;
                line-height: 30px;
                @media screen and (min-width: 768px){
                    width: 40%;
                    letter-spacing: 0.8px;
                    line-height: 40px;
                }
                
            }
        }
        .projects {
            
            h1{
                text-align: center;
                font-family: 'Nunito', sans-serif;
                margin-bottom: 40px;
            }
            .projects-grid{
                margin-top: 30px;
                display: flex;
                flex-direction: row;
                width: 90%;
                margin: auto;
                flex-wrap: wrap;
                justify-content: space-around;
                gap: 30px;
            }
            margin-bottom: 10px;
        }
        @media screen and (min-width: 768px){
            width: 90%;
            margin: auto;
            margin-top: 2%;
            border-radius: 2px;
            .header{
                flex-direction: row;
                min-height: 0;
                padding: 10px;
                .picture {
                    margin: 5px;
                    max-width: 180px;
                    width: 20%;
                }
                .name {
                    font-size: 4rem;
                }
            }
        }
    }
</style>