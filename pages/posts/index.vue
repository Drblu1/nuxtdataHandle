<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts"/>
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  components: {
    PostList
  },
  asyncData(context, callback) {
    setTimeout( () => {
      //THIS !!!!!!
      callback(null, {
        loadedPosts: [
          {
            id: '1',
            title:'wejdene',
            previewText: 'this is our first post',
            thumbnail: 'https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg'
          },
          {
            id: '2',
            title:'Best app ever',
            previewText: 'This really changed my life <3',
            thumbnail: 'https://lh3.googleusercontent.com/5PBEtJH72OUM9pbwnZC-MfCcb5-XGVTWLbNjNLbrLmbNmXe-p7geFws6vvdXqddAGvM'
          }
        ]
      })

    },1500)
  }
}
</script>


<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
