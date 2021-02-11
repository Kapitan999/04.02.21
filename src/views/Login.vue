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
         axios.get('http://37.77.104.246/api/jsonstorage/?id=300287592004b5176f120cd2cdbf9c71')
          .then(res => {
              let result = false;

              for(let i = 0; i < res.data.length; i++)
              {
                  if(res.data[i].password == this.password && res.data[i].login == this.login)
                  {
                      this.$router.push(`/users/${res.data[i].login}`)
                      this.$emit('auth', res.data[i])
                  }
              }

              if(result)
              {
                  console.log('все ок')
              }
          })
      }
  }
}
</script>
