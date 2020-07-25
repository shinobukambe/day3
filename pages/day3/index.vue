<template>
　<div class="conainer">
   <div class="jumbotron p-3 p-md-5 text-white rounded bg-dark">
    <div class="col-md-6 px-0">
      <!-- <h1 class="display-4 font-italic">Title of a longer featured blog post</h1> -->
      <h1 class="display-4 font-italic">APIっていいね</h1>
      <!-- <p class="lead my-3">Multiple lines of text that form the lede, informing new readers quickly and efficiently about what's most interesting in this post's contents.</p> -->
      <p class="lead my-3">すごく便利！</p>
      <!-- <p class="lead mb-0"><a href="#" class="text-white font-weight-bold">Continue reading...</a></p> -->
      <p class="lead mb-0"><a href="#" class="text-white font-weight-bold">続きを読む</a></p>
    </div>
   </div>
   <table class="table table-hover table-striped" >
      <thead>
        <tr>
          <th scope="col">userId</th>
          <th scope="col">id</th>
          <th scope="col">title</th>
          <th scope="col">bady</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, i) in items" :key="i">
          <th scope="row">{{item.userId}}</th>
          <td>{{item.id}}</td>
          <td>{{item.title}}</td>
          <td>{{item.bady}}</td>
        </tr>
      </tbody>
   </table>    
    <nav class="blog-pagination">
        <!-- <a class="btn btn-outline-primary" href="#">Older</a> -->
        <a class="btn btn-outline-primary" href="#">古い記事</a>
        <!-- <a class="btn btn-outline-secondary disabled" href="#">Newer</a> -->
        <a class="btn btn-outline-secondary disabled" href="#">新しい記事</a>
    </nav>
  </div>
</template>

 <script>
  import axios from 'axios'
  export default{
   data()　{
     　return{
                message:　'こんにちは',
      　　　　}
   　　　　　},
    async asyncData(){
      const url = 'https://jsonplaceholder.typicode.com/posts/'
      const params = {
          'userId': 2,
          'id': 1,
          'title':'test',
          'bady':'this is a test'
      }
      const { data } = await axios.get(url,params)
      return{
        items: data
      }
    }
 　　　　　　　　 }
 </script>


