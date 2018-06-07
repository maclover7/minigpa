<template>
  <div>
    <h1>HomePage</h1>

    <form v-on:submit.prevent="submitForm()">
      <input type="text" placeholder="Username" v-model="username" />
      <input type="text" placeholder="Password" v-model="password" />
      <input type="submit" value="Submit"></input>
    </form>
  </div>
</template>

<script>
const axios = require('axios')
debugger
export default {
  name: 'HomePage',
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    submitForm: function () {
      axios.post('http://localhost:9292/api/v1/gpa', {
        ps_type: '1',
        ps_url: 'ps2.millburn.org',
        ps_username: this.username,
        ps_password: this.password
      }).then((res) => { debugger })
    }
  }
}
</script>
