<template>
  <header>
    <div class="title">
      <h1>Eldia Jobs</h1>

    </div>
    <div class="order">
      <button @click="handleClick('title')">order by title</button>
      <button @click="handleClick('location')">order by location</button>
      <button @click="handleClick('salary')">order by salary</button>

    </div>
  </header>
  <JobsList :jobs = "jobs" :order="order"/>
</template>

<script lang="ts">
  import { defineComponent, ref  } from 'vue';
  import { Job } from './types/Job';
  import { OrderTerm } from './types/OrderTerm';
  import JobsList from './components/JobsList.vue';

  export default defineComponent({
    name: 'App',
    components: { JobsList},
    setup(){
      const jobs = ref<Job[]>([
        {title: 'Manager', location: 'Manchester', salary: 30000, id: '1'},
        {title: 'Java Engineer', location: 'Geneva', salary: 100000, id: '2'},
        {title: 'Front-end engineer', location: 'Maputo', salary: 80000, id: '3'},
        {title: 'Project Manager', location: 'Málaga', salary:40000, id: '1'},
      ]);

      const order = ref<OrderTerm>('title')

      const handleClick = (term: OrderTerm) => {
        order.value = term;
      }
      return { jobs, handleClick, order };


    },
    
    
  });
</script>

<style>
  header {
      text-align: center;
    }
    header .order {
      margin-top: 20px;
    }
    button {
      margin: 0 10px;
      color: #1195c9;
      border: 3px solid #1195c9;
      background: #d5f0ff;
      padding: 8px 16px;
      border-radius: 4px;
      cursor: pointer;
      font-weight: bold;
    }
</style>
