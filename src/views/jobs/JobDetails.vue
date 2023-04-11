<template>
    <div v-if="job">
        <h2>{{ job.title }}</h2>
        <p>The job id is {{ id }}</p>  
        <p>{{ job.details }}</p>
    </div>
    <div v-else>
        <p>Loading data...</p>
    </div>
</template>

<script>
export default {
    data () {
        return {
            job: null
        }
    },

    props: ['id'],

    mounted() {
        fetch('http://localhost:3000/jobs/' + this.id)
        .then(res => res.json())
        .then(data => this.job = data)
        .catch(err => console.log(err.message))
    }
}
</script>

<style>
    
</style>