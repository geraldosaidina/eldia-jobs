<template>
  <JobsList :jobs = "jobs"/>
</template>

<script lang="ts">
import { defineComponent, ref  } from 'vue';
import { Job } from './types/Job';
import JobsList from './components/JobsList.vue';

export default defineComponent({
  name: 'App',
  components: { JobsList},
  setup(){
    const jobs = ref<Job[]>([
      {title: 'Manager', location: 'Manchester', salary: 30000, id: '1'},
      {title: 'Java Engineer', location: 'Geneva', salary: 100000, id: '2'},
      {title: 'Front-end engineer', location: 'Maputo', salary: 80000, id: '3'},
      {title: 'Project Manager', location: 'Málaga', id: '1'},
    ]);

    return {jobs}

  },
  
  
});
</script>

<style>

</style>
