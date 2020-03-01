<template>
  <div class="apiPosts-tpl">

    <h1>{{ msg }}</h1>

    <ul id="apiPosts">
      <li v-for="post in posts" :key="post.id" class="apiPost-wrapper">
        <span class="remove" @click="removeElement(post.id)">x</span>
        <ApiPost :title="post.title" :body="post.body" :key="post.id"/>
      </li>
    </ul>
  </div>
</template>

<script>

  import ApiPost from './ApiPost'

  import axios from 'axios'

  export default {
    name: 'ApiPosts',
    components: {ApiPost},
    props: {
      msg: String
    },
    data(){
      return {
        apiposts: 'https://jsonplaceholder.typicode.com/posts',
        posts: Array,
      }
    },
    methods: {
      removeElement(index)
      {
        this.posts.splice(index, 1)
      }
    },
    mounted(){
      axios.get(this.apiposts)
        .then(response => (
                this.posts = response.data
        ))
    }
  }
</script>
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}

#apiPosts {
  display: flex;
  flex-wrap: wrap;
}

.apiPost-wrapper {
  flex: 0 0 33%;
}

.apiPost {
  padding: 15px;
  text-align: left;
}
.remove {
  color: #ff0000;
}

</style>
