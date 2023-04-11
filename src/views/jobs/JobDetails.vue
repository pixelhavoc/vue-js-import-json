<template>
    <div>
        <h2>Job Details Page</h2>
        <p>The job id is {{ id }}</p>  
    </div>
</template>

<script>
export default {
    data () {
        return {
            id: this.$route.params.id
        }
    },

    props: ['id']
}
</script>

<style>
    
</style>