<template>
  <div>
    <h2>ログインページ</h2>
    <p>
      <button type="button" @click="login">ログイン</button><br>
      <nuxt-link to="/">トップページへ戻る</nuxt-link>
    </p>
  </div>
</template>

<script>
import Cookies from 'universal-cookie'
export default {
  methods: {
    login() {
      const cookies = new Cookies()
      cookies.set('credential', 'true', {maxAge: 90})
      this.$router.push('/')
    }
  }
};
</script>

<style>
.container {
  min-height: 100vh;
  padding: 16px;
}

h3 {
  margin: 16px 0;
  padding: 8px 0;
  border-bottom: solid 1px #e5e5e5;
}

li + li {
  margin: 16px 0;
}

p {
  margin: 8px 0;
}
</style>

