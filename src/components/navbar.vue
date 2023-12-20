<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand ps-3" href="#">
        <img src="../assets/logo-blue.png" alt="Logo" width="40" height="40">
      </a>
    <!-- Botón de colapso para pantallas pequeñas -->
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    
    <!-- Contenedor para las opciones -->
    <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
      <ul class="navbar-nav">
        <li v-for="(option, index) in navbarData.options" :key="index" class="nav-item">
          <a class="nav-link" :href="option.url">{{ option.label }}</a>
        </li>
        <li class="nav-item">
          <select class="form-control">
            <option v-for="(profOption, index) in navbarData.professionalOptions" :key="index" :value="profOption.value">{{ profOption.label }}</option>
          </select>
        </li>
        <li class="nav-item">
          <select class="form-control">
            <option v-for="(compOption, index) in navbarData.companyOptions" :key="index" :value="compOption.value">{{ compOption.label }}</option>
          </select>
        </li>
        <li class="nav-item">
          <button class="btn btn-outline-primary">
            <i class="fa-solid fa-earth-americas"></i> {{ navbarData.language }}
          </button>
        </li>
        <li class="nav-item">
          <button class="btn btn-light">{{ navbarData.loginLabel }}</button>
        </li>
        <li class="nav-item">
          <button class="btn btn-primary">{{ navbarData.registerLabel }}</button>
        </li>
      </ul>
    </div>
    </nav>
</template>

<script>
export default {
  name: 'NavBar',
  props: {
  navbarData: {
    type: Object,
    required: true,
    },
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #7d7f7f;
}
</style>
