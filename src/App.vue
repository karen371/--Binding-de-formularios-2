<script>
  import Formulario from './components/Formulario.vue';
  import Respuestas from './components/Respuestas.vue';

  export default{
    data(){
      return{
        datos:{}
      };
    },
    components:{
      Formulario,
      Respuestas
    },
    methods:{
      actualizarDatos(datos){
        this.datos = {...datos};
      }
    }
  };
</script>

<template>
  <div class="contenedor">
    <Formulario @datos-actualizados="actualizarDatos"/>
    <Respuestas :datos="datos"/>
  </div>
</template>

<style scoped>
  .contenedor{
    width: 100%;
    height: 500px;
    margin:20px;
    display: flex;
  }
</style>
