<template>
    <div>
        <h6>Employees List</h6>
        <b-table striped hover :items="employees" :fields="fields"></b-table>
        <b-pagination size="md" :total-rows="employees.length" ></b-pagination>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    name: 'employees',
    data(){
        return{
            message:'Final Exam',
            employees: [],
            fields:[{
                key:'employee_id',
                sortable : true
            },
            {
                key:'first_name',
                sortable : true,

            },
            {
                key:'last_name',
                sortable : true
            },
            {
                key:'title',
                sortable : true,

            },
            {
                key:'city',
                sortable : true
            }]        
        }
    },
    mounted(){
        var instance = this
        axios
        .get('https://pacific-fjord-41656.herokuapp.com/api/employees/')
        .then(function(response){
            console.log(response)
            instance.employees = response.data.data
        })
    }
}
</script>