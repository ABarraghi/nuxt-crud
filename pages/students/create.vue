<template>
    <div class="mt-5 container">
        <h1>Student Create Page</h1>
        <div class="card">
            <div class="card-header">
                <h4>Add Student
                    <NuxtLink to="/" class="btn btn-danger float-end">Back</NuxtLink>
                </h4>
            </div>
            <div class="card-body">

                <div v-if="isLoading">
                    <div class="spinner-border" role="status">
                        <span class="sr-only">Loading...</span>
                    </div>
                </div>

                <form @submit.prevent="saveStudent">
                    <div class="mb-3">
                        <label>Name</label>
                        <input type="text" v-model="student.name" class="form-control"/>
                    </div>
                    <div class="mb-3">
                        <label>Course</label>
                        <input type="text" v-model="student.course" class="form-control"/>
                    </div>
                    <div class="mb-3">
                        <label>Email</label>
                        <input type="text" v-model="student.email" class="form-control"/>
                    </div>
                    <div class="mb-3">
                        <label>Phone</label>
                        <input type="text" v-model="student.phone" class="form-control"/>
                    </div>
                    <div class="mb-3">
                        <button type="submit" class="btn btn-primary">Save</button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "studentCreate",
    data() {
        return {
            student: {
                name: '' ,
                course: '' ,
                email: '' ,
                phone: '' 
            },
            isLoading: false,
            isLoadingTitle: 'Loading...'
        }
    },
    methods: {
        saveStudent() {
            this.isLoading = true;
            this.isLoadingTitle = "Saving";
            // alert('saving student...')
        }
    }
}

</script>


<style>

</style>