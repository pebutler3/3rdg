<template>
  <div class="home">
    <List :users="users" @toggleContactDetails="toggleContactDetails" />
  </div>
</template>

<script>
  import axios from 'axios';
  import List from '../components/List/List';

  export default {
    name: 'home',
    components: {
      List
    },
    data() {
      return {
        users: []
      };
    },
    mounted() {
      this.getUsers();
    },
    methods: {
      async getUsers() {
        const response = await axios.get('https://randomuser.me/api/?results=10');
        this.$data.users = response.data.results;
      },
      // Event passed up from List component
      toggleContactDetails(event) {
        event.currentTarget.classList.toggle('card--expanded');
      }
    }
  }
</script>
