<script>
  export default {
    data() {
      return {
        name: "Shiv Kumar",
        status: false,
        tasks: ['Destroy all humans', 'Kill Flanders', 'Learn Vue'],
        link: "https://www.google.com/"
      }
    },
  }
</script>
<template>
  <h1>{{name}}</h1>
  <p v-if="status === 'active'">User is Active</p>
  <p v-else-if="status === 'pending'">User is Pending</p>
  <p v-else>User is Inactive</p>
  <a :href="link">Click for Google</a>
  <h2>Tasks:</h2>
  <ul >
    <li v-for="task in tasks">{{task}}</li>
  </ul>
    
</template>
