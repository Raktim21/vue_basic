<template>
    <div>
        <h1>Dynamic Data</h1>
    </div>

    <input type="text" class="form-control mb-2" v-model="searchName">

    <div class="row" v-if="filterName.length !== 0" >


        <div class="col-md-6 mb-2" v-for="(post,index) in filterName" :key="index">
            <div class="card text-left">
                <img class="card-img-top" src="holder.js/100px180/" alt="">
                <div class="card-body">
                    <h4 class="card-title">{{ post.title }}</h4>
                    <p class="card-text">{{ post.body }}</p>
                </div>
            </div>
        </div>
    </div>


    <div class="row" v-else >
        <div class="col-12">
            <p class="mt-2 text-danger" >No Item found</p>
        </div>
    </div>


  
</template>

<script>
    import axios from 'axios';
    export default {

        name: 'DaynamicData',

        data() {
            return {
                posts:[],
                searchName:''
            }
        },

        computed:{
            filterName(){
                return this.posts.filter((post) => {
                    return post.title.match(this.searchName);
                })
            }
        },

        created(){
            axios.get('https://jsonplaceholder.typicode.com/posts')
            .then(response => {
                this.posts = response.data;
            })
            .catch(error=>{

                console.log(error);
            });
        }
    }
</script>

<style scoped>

</style>