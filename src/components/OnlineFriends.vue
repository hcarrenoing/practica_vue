<template>
  <div id="onlinefriends">
    <h2>Online Firends</h2>
    <div v-for="friend in friends" :key="friend.id">
      <h6 v-if="friend.online">
        {{ friend.name }}
      </h6>
    </div>
  </div>
</template>
<script>
export default {
  name: "OnlineFriends",
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
};
</script>
