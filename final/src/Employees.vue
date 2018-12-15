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
    
}
</script>