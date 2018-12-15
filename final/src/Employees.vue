<template>
    <div>
        <h1>Employees List</h1>
        <b-table striped hover :items="employees" :fields="fields" :per-page="pageSize" :current-page="pageIndex"></b-table>
        <b-pagination size="md" :total-rows="products.length" v-model="pageIndex" :per-page="pageSize"></b-pagination>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    name: 'employees',
    data(){
        return{
            message:'Final Exam',
            products: [],
            pageSize:10,
            pageIndex:1,
            fields:[{
                key:'EmployeeID',
                sortable : true
            },{
                key:'LastName',
                sortable : true
            },{
                key:'FirstName',
                sortable : true,
                // variant: 'danger'
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