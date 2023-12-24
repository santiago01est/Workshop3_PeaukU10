<template>
    <div class="containerListJob" >
        <div v-for="job in jobs" :key="job.id">
            <JobItem :job="job"></JobItem>
        </div>
    </div>
</template>

<script>
import JobItem from './jobItem.vue';
export default {
    name: 'ContainerListJob',
    components: {
        JobItem,
    },
    props: {
        jobs: {
            type: Object,
            required: true
        }
    },
};
</script>

<style scoped>
.containerListJob {
    width: 100%;
    height: 30rem;
    display: block;
    overflow-y: scroll;
    scroll-behavior: smooth;
}
</style>


