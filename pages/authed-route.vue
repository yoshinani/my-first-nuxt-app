<template>
  <div>
    <h2>認証が必要なページ</h2>
    <p>
      Cookie の 'credential' 値が Truthy な場合のみアクセス可能です。<br>
      <nuxt-link to="/">トップページへ戻る</nuxt-link>
    </p>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';
export default {
  async asyncData({ store }) {
    if (store.getters['items'].length) {
      return;
    }
    await store.dispatch('fetchItems');
  },
  computed: {
    ...mapGetters(['items'])
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

