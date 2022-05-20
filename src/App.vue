<template>
  <div id="app">
    <h2>{{ title }}</h2>
    <NavbarMenu></NavbarMenu>
    <AllFriends :friends="friends" @delete="deleteFriend($event)"></AllFriends>
    <OnlineFriends :friends="friends"></OnlineFriends>
  </div>
</template>
<script>
import NavbarMenu from "./components/NavbarMenu.vue";
import AllFriends from "./components/AllFriends.vue";
import OnlineFriends from "./components/OnlineFriends.vue";
export default {
  name: "App",
  data() {
    return {
      title: "Primer ejemplo web",
      friends: [
        { name: "Ana", online: true },
        { name: "Beatris", online: false },
        { name: "Carolina", online: true },
        { name: "Dalia", online: true },
        { name: "Elena", online: false },
      ],
    };
  },
  components: {
    NavbarMenu,
    AllFriends,
    OnlineFriends,
  },
  methods: {
    deleteFriend(friend) {
      this.friends.filter((friend) => {
        return friend.name !== friend;
      });
      var index = this.friends.indexOf(friend);

      if (index >= 0) {
        this.friends.remove(index, 1);
      }
      console.log(friend);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
