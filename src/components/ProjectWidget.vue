<template>
 <div class="project-widget">
     <h1 class="title">{{projectName}}</h1>
     <img src="../assets/logo.png" alt="logo">
     <span class="description">{{description}}</span>
     <span class="description">Used technologies:</span>
     <ul class="tech-list">
         <li class="tech" v-for="(item, index) in technologies" :key="index">{{item}}</li>
     </ul>
 </div>
</template>
<script>
export default {
    name: "ProjectWidget",
    props: ['id','projectName','description','picturePath','technologies']
}
</script>

<style lang="scss" scoped>
    .project-widget {
        
        //look
        background-color: whitesmoke;
        border: 1px solid black;
        -webkit-box-shadow: 5px 6px 9px -1px rgba(0,0,0,0.7);
        -moz-box-shadow: 5px 6px 9px -1px rgba(0,0,0,0.7);
        box-shadow: 5px 6px 9px -1px rgba(0,0,0,0.7);
        //layout
        padding: 1em;
        //flex properties
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        //animations
        transition: scale 0.2s ease-in-out;
        &:hover{
            scale: 105%;
        }
        .title{
            font-family: 'Dela Gothic One', cursive;

        }
        .description{
            font-family: 'Nunito', sans-serif;
            font-size: 1.2rem;
        }
        .tech-list{
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            width: 30%;
            list-style-type: square;
            .tech {
                font-size: 1.3rem;
                font-family: 'Rubik', sans-serif;
            }
        }
    }
</style>