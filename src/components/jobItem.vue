<template>
  <div class="job-item mb-3">

    <b-row>
        <b-col cols="1" md="1">
          <img  class="imgLogo" :src="job.image" alt="Company Logo" fluid/>
        </b-col>
      

        <div class="col ms-5" md="3" >
          <b-row>
            <b-col cols="6" md="3">
              <h4 class="textStart">{{ job.title }}</h4>
            </b-col>
            <div  class=" col d-flex align-items-center justify-content-start">
              <span class="badge border rounded-pill bg-light text-dark p-2 mx-1" v-for="tag in job.tags" :key="tag"
                variant="secondary">
                {{ tag }}
              </span>
            </div>
          </b-row>
        

          <b-row class="mt-3 d-flex align-items-center justify-content-between">
            <b-col md="2" class="font-weight-bold textStart">{{ job.company }}</b-col>
            <b-col md="2" class="font-weight-bold textStart">{{ job.location }}</b-col>
            <b-col md="2" class="font-weight-bold textStart">{{ job.salary }}</b-col>
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
  width: 100px;
  height: 100px;
  object-fit: cover;
  border-radius: 50%;
  
}

.textStart {
  text-align: start;
}
</style>
