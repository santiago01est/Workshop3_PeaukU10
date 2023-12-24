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
        ],
        optionsCargo:[
        { label: 'Todos los cargos', value: 'opcion0' },
        { label: 'Comercio Exterior', value: 'opcion1' },
          { label: 'Agente de Aduanero', value: 'opcion2' },
          { label: 'Agente de Carga Internacional', value: 'opcion3' },
          { label: 'Analista de Comercio Internacional', value: 'opcion4' },
          { label: 'Comercio Exterior - Otro', value: 'opcion5' },
          { label: 'Gerente de Comercio Internacional', value: 'opcion6' },
          { label: 'Contabilidad y Finanzas', value: 'opcion7' },
          { label: 'Auxiliar contable', value: 'opcion8' },
          { label: 'Contabilidad - Otro', value: 'opcion9' },
          { label: 'Contador de cobros y pagos', value: 'opcion10' },
          { label: 'Contador de flujo de caja', value: 'opcion11' },
          { label: 'Contador de Impuestos', value: 'opcion12' },
          { label: 'Contador Principal', value: 'opcion13' },
          { label: 'Diseño', value: 'opcion14' },
          { label: 'Diseñador Gráfico', value: 'opcion15' },
          { label: 'Diseñador Industrial', value: 'opcion16' },
          { label: 'Diseñador UI/UX', value: 'opcion17' },
          { label: 'Logística y Transporte', value: 'opcion18' },
          { label: 'Analista de Logística', value: 'opcion19' },
          { label: 'Analista de Transporte', value: 'opcion20' },
          { label: 'Gerente de Logística', value: 'opcion21' },
          { label: 'Gerente de Transporte', value: 'opcion22' },
          { label: 'Logística y Transporte - Otro', value: 'opcion23' },
          { label: 'Marketing', value: 'opcion24' },
          { label: 'Community Manager', value: 'opcion25' },
          { label: 'Estratega de SEO', value: 'opcion26' },
          { label: 'Generador de Contenido', value: 'opcion27' },
          { label: 'Marketing - Otro', value: 'opcion28' },

        ],
        optionsMoneda:[
        {label: "Moneda", value: "opcion0"},
          {label: "Balboa", value: "opcion1"},
          {label: "Belize Dollar", value: "opcion2"},
          {label: "Bolivar", value: "opcion3"},
          {label: "Boliviano", value: "opcion4"},
          {label: "Canadian Dollar", value: "opcion5"},
          {label: "Colón", value: "opcion6"},
          {label: "Córdoba", value: "opcion7"},
          {label: "Dollar", value: "opcion8"},
          {label: "Euro", value: "opcion9"},
          {label: "Guaraní", value: "opcion10"},
          {label: "Lempira", value: "opcion11"},

        ],
        optionsUbicacion:[
        {label: "Bogotá", value: "opcion0"},
        {label: "Barrancabermeja", value: "opcion1"},
        {label: "Santiago de Cali", value: "opcion2"},
        {label: "Bucaramanga", value: "opcion3"},
        {label: "Tuluá", value: "opcion4"},
        {label: "Aguachica", value: "opcion5"},
        {label: "Palmira", value: "opcion6"},
        {label: "La Union", value: "opcion7"},
        {label: "Cúcuta", value: "opcion8"},
        {label: "Antioquia", value: "opcion9"},
          
        ]
      },
      jobs: [
        {
          id: 1,
          image: require('@/assets/empresa01.jpg'),
          title: 'Técnico de soporte Medellin',
          tags: ['attitude to service', 'electronics', 'systems administration'],
          company: 'Intexus',
          location: 'Medellín',
          salary: '$ 1.2M - 1.3M COP',
          numVacancies: 1,
          date: "3 days ago",
          benefits: [{
            benefit: 'Trabajo remoto parcial',
            icon: 'fa-solid fa-location-dot'
          },
          {
            benefit: 'Seguros',
            icon: 'fa-solid fa-lock'
          },
          {
            benefit: 'Fiesta de fin de año',
            icon: 'fa-regular fa-face-grin-wink'
          }]
        },
        {
          id: 2,
          image: require('@/assets/empresa02.jpg'),
          title: 'Maquetador Web',
          tags: ['layout', 'css3', 'html'],
          company: 'Timbergrove Solutions',
          location: 'Remote',
          salary: '$ 1K - 2K USD',
          numVacancies: 1,
          date: "5 days ago",
          
        },
        {
          id: 3,
          image: require('@/assets/empresa03.png'),
          title: 'Director de proyectos',
          tags: ['project management', 'project coordination', 'agile methodologies (scrum)'],
          company: 'Intexus',
          location: 'Bogotá',
          salary: '$ 5M - 6M COP',
          numVacancies: 1,
          date: "5 days ago",
          benefits: [{
            benefit: 'Trabajo remoto parcial',
            icon: 'fa-solid fa-location-dot'
          },
          {
            benefit: 'Seguros',
            icon: 'fa-solid fa-lock'
          },
          {
            benefit: 'Fiesta de fin de año',
            icon: 'fa-regular fa-face-grin-wink'
          }]
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
          benefits:[{
            benefit:'Curso de ingles',
            icon:'fa-solid fa-globe'
          }]
        },
        {
          id: 5,
          image: require('@/assets/empresa05.png'),
          title: 'DESARROLLADOR FRONTEND ANGULAR',
          tags: ['JavaScript', 'TypeScript', 'Angular'],
          company: 'Timbergrove Solutions',
          location: 'Remoto',
          salary: '$2K - 5K USD',
          numVacancies: 1,
          date: "2 days ago",
          benefits: [{
            benefit: 'Trabajo remoto parcial',
            icon: 'fa-solid fa-location-dot'
          },
          {
            benefit: 'Seguros',
            icon: 'fa-solid fa-lock'
          },
          {
            benefit: 'Fiesta de fin de año',
            icon: 'fa-regular fa-face-grin-wink'
          }]
        },
        {
          id: 6,
          image: require('@/assets/empresa00.svg'),
          title: 'Data Enginner',
          tags: ['SQl', 'Eti', 'Python'],
          company: 'Confidencial',
          location: 'Medellín',
          salary: '$ 8m - 12M COP',
          numVacancies: 1,
          date: "7 days ago",
          benefits: [{
            benefit: 'Trabajo remoto parcial',
            icon: 'fa-solid fa-location-dot'
          },
          {
            benefit:'Curso de ingles',
            icon:'fa-solid fa-globe'
          },
          {
            benefit: 'Trabajo remoto parcial',
            icon: 'fa-solid fa-location-dot'
          },
          {
            benefit: 'Fiesta de fin de año',
            icon: 'fa-regular fa-face-grin-wink'
          }]
        },
        {
          id: 7,
          image: require('@/assets/empresa02.jpg'),
          title: 'Maquetador Web',
          tags: ['layout', 'css3', 'html'],
          company: 'Timbergrove Solutions',
          location: 'Remote',
          salary: '$ 1K - 2K USD',
          numVacancies: 1,
          date: "5 days ago",
          
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
  color: black;
  font-size: 1rem;
}
</style>
