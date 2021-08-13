<template>
        <div>
                <h1> Users data </h1>
                <table id="t01">
                        <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Address</th>
                                <th>Action</th>
                        </tr>
                         <tr v-for="user in users" v-bind:key="user.id">
                                <td>{{user.name}}</td>
                                <td>{{user.email}}</td>
                                <td>{{user.address}}</td>
                                <td><button v-on:click="deleteUser(user.id)">Delete</button></td>
                        </tr>
                </table>
        </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)
export default {
        name: "Users",
        data()
        {
                return {users:null}

        },
        methods:
        {
                getUsers()
                {
                         this.axios.get('http://localhost3001/users').this((result)=>{
                        console.warn(result)
                        this.users=result.data
                })
                        
                },deleteUser(id)
                {

                          this.axios.delete('http://localhost3001/users/'+id).this((result)=>{
                        console.warn(result)
                        this.getUsers
                })

                }
                     
        },
        mounted()
        {
             
             this.getUsers()

        }
}
</script>

<style scoped>
table{
        width:100%;
}
table, th, td{
        border: 1px solid black;
        border-collapse: collapse;
}
th, td{
        padding: 15px;
        text-align: left;
}
#t01 tr:nth-child(even) {
  background-color: #eee;
}
#t01 tr:nth-child(odd) {
 background-color: #fff;
}

</style>