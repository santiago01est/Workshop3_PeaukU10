<template>
  <div id="app">
    <NavBar :navbarData="navbarDataInfo"/>
    <!-- aqui la barra de busqueda-->
    <!-- aqui la lista de empleos-->
  </div>
</template>

<script>
import NavBar from './components/navbar.vue'

export default {
  name: 'App',
  components: {
    NavBar
  },
  data(){
    return{
      navbarDataInfo: {
        options: [
          { label: 'Empleos', url: '#' },
          { label: 'Bootcamp', url: '#' },
          { label: 'Sobre Nosotros', url: '#' },
        ],
        professionalOptions: [
          { label: 'Para profesionales', value: 'opcion1' },
          { label: 'Inicio', value: 'opcion2' },
          { label: 'Empleos', value: 'opcion3' },
          { label: 'Cursos y retos', value: 'opcion4' },
        ],
        companyOptions: [
          { label: 'Para empresas', value: 'opcion1' },
          { label: 'Publicar empleo', value: 'opcion2' },
          { label: 'Nuestro proceso', value: 'opcion3' },
          { label: 'Precios', value: 'opcion4' },
        ],
        language: 'Español',
        loginLabel: 'Ingresa',
        registerLabel: 'Regístrate',
      },
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
#app {
  font-family: 'Inter', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #F8F9FA;
  color: black;
}
</style>
