<script>
    export default{
        props:{
            datos:{
                type:Object,
                default(){
                    return{
                        titulo:'',
                        emoji:'',
                        apreciacion:'',
                        competencias:[],
                        opinion:''
                    }
                },
            },
        }
    };
</script>
<template>
    <div class="Respuesta">
            <p class="emoji">{{datos.emoji}}</p>
            <h3>{{datos.titulo}}</h3>
            <p>Y me parece {{datos.apreciacion}}</p>
            <p>He aprendido:</p>
        <ul>
            <li v-for="competencia in datos.competencias" :key="competencia">{{competencia}}</li>
        </ul>
            <p>Mi opinion hasta ahora del framework es:</p>
            <p>{{datos.opinion}}</p>
    </div>
</template>
<style scoped>
    .Respuesta {
        width: 50%;
        margin: 0 auto;
        padding: 20px;
        background-color: #f5f5f5;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        text-align: left;
    }
    .emoji {
        font-size: 40px;
        margin-bottom: 10px;
    }
    h3 {
        font-size: 1.8rem;
        margin: 10px 0;
        color: #333;
    }
    p {
        font-size: 1rem;
        margin: 5px 0;
        color: #555;
    }
    .opinion {
        font-style: italic;
        color: #666;
    }
    ul {
        list-style-type: disc;
        margin-left: 20px;
        color: #444;
    }
    li {
        font-size: 1rem;
    }
</style>