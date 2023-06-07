<template>
  <div>
    <Nav/>
    <div class="row">
      <!-- <div class="col-md-4">
        <Allfriends :friends="friends" @unfriend="deleteFriend"/>
      </div>
      <div class="col-md-4">
        <Onlinefriend :friends="friends" @unfriend="deleteFriend" />
      </div>
      <div class="col-md-4">
        <Offlinefriends :friends="friends" @unfriend="deleteFriend" />
      </div> -->

      <div class="col-12">
        <DaynamicData/>
      </div>
    </div>
  </div>
</template>

<script>
  import Nav from './components/Navbar.vue'
  // import Allfriends from './components/Allfriends.vue'
  // import Onlinefriend from './components/Onlinefriend.vue'
  // import Offlinefriends from './components/Offlinefriends.vue'
  import DaynamicData from './components/DynamicData.vue'


  export default {
    name: 'App',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',

        friends:[ 
          {name: 'John', online: true},
          {name: 'Mary', online: false},
          {name: 'Gary', online: true},
          {name: 'Sue', online: false},
          {name: 'Greg', online: true},
          {name: 'Beth', online: false},
          {name: 'Steve', online: true},
          {name: 'Sue', online: false},
          {name: 'Greg', online: true},
        ]
      }
    },
    
    methods: {
      deleteFriend(payload){
        this.friends = this.friends.filter((friend) => friend.name !== payload);
      }
    },

    components: {
      Nav,
      // Allfriends,
      // Onlinefriend,
      // Offlinefriends,
      DaynamicData
    }
    
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
