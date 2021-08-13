<template>
        <div> 
                <h2>Submit Form Data To API</h2>
                <form @submit="submitData" method="post">
                        <input type="text" name="title" v-model="post.title" placeholder="title"/> <br><br>
                        <input type="text" name="author" v-model="post.author" placeholder="author"/> <br><br>
                        <button type="submit"> Post Data</button>

                </form>

        </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)

export default {
        name: "PostComponet",
        data()
        {
                return{
                        post:{
                                title:null,
                                author:null
                        }

                }
        },
        methods:
        {
                submitData(e)
                {       
                        this.axios.post('http://localhost:3000/posts', this.post).then((result)=>{
                                 console.warn("result" ,result)
                        })
                       
                        e.preventDefault();

                }

        }
        
}
</script>