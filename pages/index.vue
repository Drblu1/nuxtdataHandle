<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news!</h1>
    </section>
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
    console.log("Async dans index est excécuté");
    setTimeout( () => {
      //THIS !!!!!!
      callback(new Error(), {
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
  },
/*  data() {
    return {
      loadedPosts: []
    }
  },*/
  created() {

  }
}
</script>


<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
  background-image: url('~assets/images/main-page-background.jpg');
  background-position: center;
  background-size: cover;
}

.intro h1 {
  position: absolute;
  top: 10%;
  left: 5%;
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 3px 3px 3px black;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}

.featured-posts {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
