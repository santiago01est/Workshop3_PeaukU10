<template>
  <section class="d-flex justify-content-center py-4 m-1 px-5">
    <button class="btn btn-outline-secondary"><i class="fa-solid fa-magnifying-glass"></i></button>
    <input class="form-control  mx-5" placeholder="Busca por cargo, salario, ubicación o empresa" style="width: 40rem;" />
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalArea>Area <i class="fa-solid fa-caret-down"></i></button>
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalCargo>Cargo <i class="fa-solid fa-caret-down"></i></button>
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalSalario>Salario <i class="fa-solid fa-caret-down"></i></button>
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalUbicacion>Ubicación <i class="fa-solid fa-caret-down"></i></button>






    <!--Modales-->
    <b-modal id="modalArea" title="Elige un areá de trabajo" style="background-color: #1d976c;">
      <lu class="navbar-nav">
        <li v-for="(option, index) in searchData.optionsArea" :key="index" class="nav-item d-flex m-0 p-0">
          <input type="checkbox" class="custom-control mx-2 custom-checkbox"/>
          <label class="nav-item" >{{ option.label }}</label>
        </li>
      </lu>
    </b-modal>
    
    <b-modal id="modalCargo" title="BootstrapVue">
      <p class="my-4">Cargo</p>
    </b-modal> 
    
    <b-modal id="modalSalario" title="BootstrapVue">
      <p class="my-4">Salario</p>
    </b-modal> 
    
    <b-modal id="modalUbicacion" title="BootstrapVue">
      <p class="my-4">Ubicabion</p>
    </b-modal>
  </section>
</template>

<script>
export default {
  name: 'SearchNav',
  props: {
    searchData: {
      type: Object,

    }
  }
}

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section {
  background-color: #3a8ced;
}
button{
  border-radius: 50px;
}
</style>