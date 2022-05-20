<template>
  <div id="allfriends">
    <h2>All Friends</h2>
    <div v-for="friend in friends" :key="friend.id">
      <h6 @click="unfriend(friend.name)">
        {{ friend.name }}
      </h6>
    </div>
  </div>
</template>
<script>
export default {
  name: "AllFriends",
  props: ["friends"],
  data() {
    return {
      /*friends: [
        { name: "Ana", online: true },
        { name: "Beatris", online: false },
        { name: "Carolina", online: true },
        { name: "Dalia", online: true },
        { name: "Elena", online: false },
      ],*/
    };
  },
  methods: {
    unfriend(name) {
      this.$emit("delete", name);
      //this.$emit("delete", { name });
    },
  },
};
</script>
