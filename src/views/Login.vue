<template>
    <div>
        <input  v-model="login" type="text" placeholder="Логин">
        <input  v-model="password" type="password" placeholder="Пароль">
         <input  type="submit" value="Войти" @click="auth">
    </div>
</template>

<script>
import axios from 'axios'

export default {
  data()
  {
      return{
          login: '',
          password: '',
      }
  },
  methods: {
      auth()
      {
          axios.get('h')
      }
  }
}
</script>
