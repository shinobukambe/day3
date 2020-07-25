<template>
  <div class="container">
   {{message}}
  </div>
</template>

<script>
  import axios from 'axios'
  export default{
  data() {
    return{
      message: 'Hellow'
    }
  },
  async asyncData() {
      const response = await axios.get('https://jsonplaceholder.typicode.com/posts/1')
      console.log(response)
  }
  }
</script>


