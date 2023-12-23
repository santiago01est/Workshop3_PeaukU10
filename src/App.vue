<template>
  <div id="app">
    <NavBar :navbarData="navbarDataInfo"/>
    <SearchNav :searchData="searchDataInfo"/>
    <!-- aqui la lista de empleos-->
    <ContainerListJob :jobs="jobs"/>
  </div>
</template>

<script>
import NavBar from './components/navbar.vue'
import SearchNav from './components/search.vue';
import ContainerListJob from './components/containerListJob.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    SearchNav,
    ContainerListJob
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
      searchDataInfo:{
        optionsArea:[
          {label:'Comercio'},
          {label:'Contabilidad y finanzas'},
          {label:'Diseño'},
          {label:'Logística y Transporte'},
          {label:'Marketing'},
          {label:'Otro'},
          {label:'Reclutamiento'},
          {label:'Servicio al cliente'},
          {label:'Tecnología'},
          {label:'Ventas'},
        ]
      },
      jobs: [
        {
          id: 1,
          image: require('@/assets/empresa01.jpg'),
          title: 'Frontend Developer',
          tags: ['JavaScript', 'Vue', 'CSS'],
          company: 'TechCorp',
          location: 'Remote',
          salary: '$70k - $90k',
          numVacancies: 2,
          date: "2 days ago",
          //Aqui irá el grupo de emojis de ventajas de trabajar con ellos [quitar status por lo mencionado]
          status: 'Actively Hiring'
        },
        {
          id: 2,
          image: require('@/assets/empresa02.jpg'),
          title: 'Frontend Developer',
          tags: ['JavaScript', 'Vue', 'CSS'],
          company: 'TechCorp',
          location: 'Remote',
          salary: '$70k - $90k',
          numVacancies: 2,
          date: "2 days ago",
          status: 'Actively Hiring'
        },
        {
          id: 3,
          image: require('@/assets/empresa03.png'),
          title: 'Frontend Developer',
          tags: ['JavaScript', 'Vue', 'CSS'],
          company: 'TechCorp',
          location: 'Remote',
          salary: '$70k - $90k',
          numVacancies: 2,
          date: "2 days ago",
          status: 'Actively Hiring'
        },
        {
          id: 4,
          image: require('@/assets/empresa04.png'),
          title: 'Frontend Developer',
          tags: ['JavaScript', 'Vue', 'CSS'],
          company: 'TechCorp',
          location: 'Remote',
          salary: '$70k - $90k',
          numVacancies: 2,
          date: "2 days ago",
          status: 'Actively Hiring'
        },
        {
          id: 5,
          image: require('@/assets/empresa02.jpg'),
          title: 'Frontend Developer',
          tags: ['JavaScript', 'Vue', 'CSS'],
          company: 'TechCorp',
          location: 'Remote',
          salary: '$70k - $90k',
          numVacancies: 2,
          date: "2 days ago",
          status: 'Actively Hiring'
        },
        // ... más trabajos
      ]

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
