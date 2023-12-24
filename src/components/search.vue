<template>
  <section class="d-flex justify-content-center py-4 m-1 px-5">
    <button class="btn btn-outline-secondary"><i class="fa-solid fa-magnifying-glass"></i></button>
    <input class="form-control  mx-5" placeholder="Busca por cargo, salario, ubicación o empresa" style="width: 40rem;" />
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalArea>Area <i
        class="fa-solid fa-caret-down"></i></button>
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalCargo>Cargo <i
        class="fa-solid fa-caret-down"></i></button>
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalSalario>Salario <i
        class="fa-solid fa-caret-down"></i></button>
    <button class="btn btn-outline-light mt-1 mb-1" v-b-modal.modalUbicacion>Ubicación <i
        class="fa-solid fa-caret-down"></i></button>






    <!--Modales-->
    <b-modal id="modalArea" title="Elige un areá de trabajo" centered>
      <lu class="navbar-nav">
        <li v-for="(option, index) in searchData.optionsArea" :key="index" class="nav-item d-flex m-0 p-0">
          <input type="checkbox" class="custom-control mx-2 custom-checkbox" />
          <label class="nav-item">{{ option.label }}</label>
        </li>
      </lu>
      <template #modal-footer="{ ok, cancel }">
          <b-button size="md" variant="outline-secondary" @click="cancel('cancel')">
            Cerrar
          </b-button>
          <b-button size="md" variant="primary" @click="ok('ok')">
            Aplicar
          </b-button>
      </template>
    </b-modal>

    <b-modal id="modalCargo" centered title="Elige uno o más cargos">
      <ul>
        <li class="nav-item d-flex">
          <select class="form-control btn btn-outline-secondary" style="color: #000;">
            <option v-for="(optionCargo, index) in searchData.optionsCargo" :key="index" :value="optionCargo.value">
              {{ optionCargo.label }}</option>
          </select>

        </li>
      </ul>
      <template #modal-footer="{ ok, cancel }">
          <b-button size="md" variant="outline-secondary" @click="cancel('cancel')">
            Cerrar
          </b-button>
          <b-button size="md" variant="primary" @click="ok('ok')">
            Aplicar
          </b-button>
      </template>
    </b-modal>

    <b-modal id="modalSalario" centered title="Rango salarial">
      <select class="form-control btn" style="color: #000;">
        <option v-for="(optionMoneda, index) in searchData.optionsMoneda" :key="index" :value="optionMoneda.value">
          {{ optionMoneda.label }}</option>
      </select>
      <div class="d-flex justify-content-around mt-3">
        <input type="number" placeholder="MIN" class="form-control mx-2" />
        <input type="number" placeholder="MAX" class="form-control mx-2" />
      </div>
      <template #modal-footer="{ ok, cancel }">
          <b-button size="md" variant="outline-secondary" @click="cancel('cancel')">
            Cerrar
          </b-button>
          <b-button size="md" variant="primary" @click="ok('ok')">
            Aplicar
          </b-button>
      </template>
    </b-modal>

    <b-modal id="modalUbicacion" centered title="Elige una ubicación">
      <select class="form-control btn" style="color: #000;">
        <option v-for="(optionUbicacion, index) in searchData.optionsUbicacion" :key="index"
          :value="optionUbicacion.value">{{ optionUbicacion.label }}</option>
      </select>
      <template #modal-footer="{ ok, cancel }">
          <b-button size="md" variant="outline-secondary" @click="cancel('cancel')">
            Cerrar
          </b-button>
          <b-button size="md" variant="primary" @click="ok('ok')">
            Aplicar
          </b-button>
      </template>
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

button {
  border-radius: 50px;
}</style>