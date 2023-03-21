<template>
  <form @submit.prevent="submitForm">
    <div>
      <label for="username">ID: </label>
      <input id="username" type="text" v-model="username"/>
    </div>
    <div>
      <label for="password">PW: </label>
      <input id="password" type="password" v-model="password"/>
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  name: 'DataBindingForm',
  components: {},
  computed: {},
  watch: {},
  data(){
    return {
      username: '',
      password: ''
    }
  },
  setup(){},
  created(){},
  mounted(){},
  unmounted(){},
  methods: {
    async submitForm(e) {
      const url = 'https://jsonplaceholder.typicode.com/users'
      const data = {
        username: this.username,
        password: this.password
      }
      let response;
      try {
        response = await axios.post(url, data);
      }catch(error) {
        console.log(error)
      }
    }
  }
}
</script>

<style>

</style>