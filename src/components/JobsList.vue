<template>
    <div class="job-list">
        <ul>
            <li v-for="job in jobs" :key="job.id">
                <h2>{{ job.title }} in {{ job.location }}</h2>
                <div class="salary">
                    <p>{{ job.salary }} USD</p>
                </div>
                <div class="description">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellat nulla, repudiandae illum fuga esse quis dignissimos quo, eligendi ab ducimus minima illo voluptatem facere ex porro veritatis est asperiores nemo?</p>
                </div>

            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { Job } from '@/types/Job';

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>
        }
    }
})
</script>

<style scoped>

</style>
