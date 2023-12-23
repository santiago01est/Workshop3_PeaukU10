<template>
  <div class="job-item mb-3">

    <b-row>
        <div class="col-auto ms-2">
          <img  class="imgLogo mx-0" :src="job.image" alt="Company Logo" fluid/>
        </div>
      

        <div class="col ms-5" >
          <b-row class="d-flex align-items-center justify-content-start">
            <div class="col-auto">
              <h4 class=" textTitle">{{ job.title }}</h4>
            </div>
            <div  class="col d-flex align-items-center justify-content-start">
              <span class="badge border rounded-pill bg-light text-dark p-1 mx-1" v-for="tag in job.tags" :key="tag"
                variant="secondary">
                {{ tag }}
              </span>
            </div>
          </b-row>
        

          <b-row class="mt-2 me-5 d-flex align-items-center justify-content-between">
            <b-col md="2" class="font-weight-bold textStart"><i class="fa-solid fa-city"></i> {{ job.company }}</b-col>
            <b-col md="2" class="font-weight-bold textStart"><i class="fa-solid fa-location-dot"></i> {{ job.location }}</b-col>
            <b-col md="2" class="font-weight-bold textStart"><i class="fa-regular fa-money-bill-1"></i> {{ job.salary }}</b-col>
            <b-col md="2" class="font-weight-bold textStart"><i class="fa-solid fa-user-group"></i> {{ job.numVacancies }}</b-col>
            <b-col md="2" class="font-weight-bold textStart"><i class="fa-regular fa-calendar"></i> {{ job.date }}</b-col>
            <b-col md="2" class="font-weight-bold textStart" v-if="job.status">{{ job.status }}</b-col>
          </b-row>
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
