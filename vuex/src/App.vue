<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    <router-view/>
    {{ $store.state.count }}
    <br>
    <ul>
      <li v-for="user in visibleUsers" :key="user.id">
      {{ user.id }} : {{ user.name }} : {{ user.isVisible }}
      </li>
    </ul>
    <br>
    {{ getUserById.name }}
  </div>
</template>

<script>
export default {
  computed:{
    visibleUsers(){
      return this.$store.getters.visibleUsers
    },
    getUserById(){
      // id2のユーザーを表示
      return this.$store.getters.getUserById(2)
    }
  }
}
</script>

