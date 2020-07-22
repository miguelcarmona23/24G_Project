<template>
  <div class="video-player">
      <div class="video-container">
      <iframe width="640" height="360" :src="this.activeVideo.youtubeURL" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
      <h3>{{this.activeVideo.title}}</h3>
      <div class="row">
        <p>{{this.activeVideo.views}} views</p>
        <p>{{this.activeVideo.likes}} <button @click="addLike">Like</button></p>
    </div>
</div>
    <div class="video-list">
    <div @click="chooseVideo(video)" :key="video.id" v-for="video in videos" class="thumbnail">
        <div class="thumbnail-img">
          <img :src="video.thumbnail" />
        </div>
        <div class="thumbnail-info">
          <h3>{{video.title}}</h3>
          <p>{{video.creator}}</p>
          <p class="thumbnail-views">{{video.views}} Views</p>
        </div>
    </div>
</div>
</div>
</template>

<script>

let videos = [
  {
    id: 1,
    title: 'Who is 24G?',
    thumbnail:
      'https://static-email-hosting.s3.amazonaws.com/24G_Test_Project/videos/who_is_24g.jpg',
    youtubeURL: 'https://static-email-hosting.s3.amazonaws.com/24G_Test_Project/videos/who_is_24g.mp4',
    creator: '24G',
    likes: 0,
    views: 0
  },
  {
    id: 2,
    title: 'CES Overview',
    thumbnail:
      'https://static-email-hosting.s3.amazonaws.com/24G_Test_Project/videos/ces_overview.jpg',
    youtubeURL: 'https://static-email-hosting.s3.amazonaws.com/24G_Test_Project/videos/ces_overview.mp4',
    creator: '24G',
    likes: 0,
    views: 0
  },
  {
    id: 3,
    title: 'Future of Drones',
    thumbnail:
      'https://static-email-hosting.s3.amazonaws.com/24G_Test_Project/videos/future_of_drones.jpg',
    youtubeURL: 'https://static-email-hosting.s3.amazonaws.com/24G_Test_Project/videos/future_of_drones.mp4',
    creator: '24G',
    likes: 0,
    views: 0
  }
]

export default {
  name: 'VideoPlayer',
  data () {
    return {
      videos,
      activeVideo: videos[0]
    }
  },
  methods: {
    chooseVideo (video) {
      // SET VIDEO AS ACTIVE VIDEO
      this.activeVideo = video
      // INCREASE THE VIDEOS VIEWS BY 1
      video.views += 1
    },
    addLike () {
      this.activeVideo.likes += 1
    }
  }
}
</script>

<style scoped>
  .thumbnail{
    display:flex;
  }
  .thumbnail img{
    width:168px;
    cursor: pointer;
}

.thumbnail-info{
    margin-left:20px;
}

.thumbnail h3{
    font-size:16px;
}

h3,
p{
    margin:0;
    padding:0;
}

.thumbnail-views{
    font-size:14px;
}
.video-player{
    display:flex;
    width:1200px;
    margin:auto;
}

.video-container{
    margin-right:40px;
}

.row{
    display:flex;
    justify-content:space-between;
}

button{
    background:#D0021B;
    color:white;
    border:none;
    padding:10px 20px;
}

button:hover {
        cursor: pointer;
}
</style>
