<template>
  <div class="job-item mb-3 rounded">

    <b-row>
        <div class="col-auto ms-2">
          <img  class="imgLogo mx-0" :src="job.image" alt="Company Logo" fluid/>
        </div>
      

        <div class="col ms-5" >
          <b-row class="d-flex align-items-center justify-content-start">
            <div class="col-auto">
              <h5 class=" textTitle">{{ job.title }}</h5>
            </div>
            <div  class="col d-flex align-items-center justify-content-start">
              <span class="badge border rounded-pill bg-white text-dark p-1 mx-1" v-for="tag in job.tags" :key="tag"
                variant="secondary">
                {{ tag }}
              </span>
            </div>
          </b-row>
        

          <div class="row mt-2 me-5 d-flex align-items-center justify-content-between">
            <div class="col col-3  textStart"><i class="fa-solid fa-city"></i> {{ job.company }}</div>
            <div class="col col-1  textStart"><i class="fa-solid fa-location-dot"></i> {{ job.location }}</div>
            <div class=" col-1  textStart"><i class="fa-regular fa-money-bill-1"></i> {{ job.salary }}</div>
            <div class=" col-1  textStart"><i class="fa-solid fa-user-group"></i> {{ job.numVacancies }} vacante</div>
            <div class=" col-1  textStart"><i class="fa-regular fa-calendar"></i> {{ job.date }}</div>
              <div class=" col-2">
              <span class="badge border rounded-pill bg-white text-dark p-2 mx-1" v-for="benefit in job.benefits" :key="benefit"
                variant="secondary" :title="benefit.benefit">
                <i :class="benefit.icon"></i>
              </span>
              </div>
          </div>
        </div>

      
    </b-row>

  </div>
</template>

<script>
export default {
  name: 'JobItem',
  props: {
    job: {
      type: Object,
      required: true
    }
  },
};
</script>

<style scoped>
.job-item {
  background-color: white;
  border: 1px solid #dee2e6;
  /* Bootstrap color for borders */
  border-radius: 0.25rem;
  padding: 1rem;
  width: 100%;
  transition: box-shadow 0.3s ease-in-out;
}

.job-item:hover {
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3); /* Sombra negra */
    }

.imgLogo {
  width: 80px;
  height: 80px;
  object-fit: cover;
  border-radius: 50%;
  
}

.textStart {
  display: block;
  text-align: start;
  width: auto;
  color: dimgrey;
}

.textTitle{
  color:#1d1b1b;
  font-weight: bold;
}
</style>
