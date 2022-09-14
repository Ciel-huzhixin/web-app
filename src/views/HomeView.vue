<template>
  <div class="home">
    <ul>
      <li v-for="user in users" :key="user.username">{{ user.username }} - {{ user.age }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'HomeView',
  data() {
    return {
      users: []
    }
  },
  async created() {
    const res = await axios.get('http://150.158.31.46:4000/api/users');
    this.users = res.data;
    console.log(res);
  }
}
</script>
