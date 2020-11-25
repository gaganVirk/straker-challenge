<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <div class="" v-if="selectedUser==0">
      <ul id="list-users" class="text-center">
        <li v-for="user in users" :key="user.id" @click="selectUser(user.id)">{{user.name}}</li>
      </ul>
    </div>
    <div v-else>
        <CButton @click="selectedUser = 0"
            color="info"
            position="left"
            size="sm"
            class="pull-left"
          >
              Go Back
          </CButton>
    </div>
    <Posts v-bind:userid="selectedUser"></Posts>
  </div>
</template>

<script>
export default {
  name: 'Home',
  components: {
    Posts: () => import('./Posts'),
  },
  props: {
    msg: String
  },
  data() {
    return {
      users: null,
      selectedUser: 0,
    }
  },
  mounted() {
    this.getUsers();
  },
  methods: {
    async getUsers() {
      const response = await fetch("https://jsonplaceholder.typicode.com/users")
      this.users = await response.json();
    },
    selectUser(userId) {
      this.selectedUser = userId;
    },
  },
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
ul {
  li {
    margin-top: 14px;
    cursor: pointer;
    font-size: 2em;
    font-family: sans-serif;
    list-style-type: none;
  }
}
button {
  cursor: pointer;
  position: relative;
}

h1 {
  text-align: center;
}

</style>
