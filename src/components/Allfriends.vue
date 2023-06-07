<template>
    <div>
        <div class="card ">
            <div class="card-body">
                <h4 class="card-title">All Friends</h4>
                <table class="table">
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Status</th>
                            <th>Action</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(friend,index) in friends" :key="index">
                            <td scope="row"> {{ friend.name }}</td>
                            <td><span :class="[friend.online ? 'text-success' : 'text-danger']">{{ friend.online }}</span></td>
                            <td>
                                <a @click="unfriend(friend.name)" class="btn btn-danger text-white">Delete</a>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>

    export default ({

        name: 'All-friends',
        props: ['friends'],

        data(){
            return {}
        },

        
        methods: {
            unfriend(friendName){
                this.$emit('unfriend',friendName);
            }
        }
    
        
    })
</script>


<style scoped>

    nav li {
        list-style-type: none;

    }

</style>