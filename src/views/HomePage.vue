<template>
<div>
  <ImgBanner imgSrc="https://source.unsplash.com/random">
    <div style="line-height:1.2em;" slot="text">배너없다<br></div>
  </ImgBanner>
  <v-container>
    <!-- About Me -->
    <v-layout my-5>
      <v-flex class="aboutMe" :class="$mq" xs8>
        <h2 class="headline mb-3">About Me</h2>
        <p class="mr-4">안녕하세요, 뭐하시나요!<br></p>
      </v-flex>


      <v-flex class="profileImg" :class="$mq" xs4>
        <v-img :src="getImgUrl('profile.png')" aspect-ratio="1.5" />
      </v-flex>
    </v-layout>

    <!-- Portfolio -->
    <v-layout my-5>
      <v-flex xs12>
        <router-link to="/portfolio">
          <h2 class="headline my-5 text-xs-center">Portfolio</h2>
        </router-link>
        <PortfolioList></PortfolioList>
      </v-flex>
    </v-layout>

    <!-- Post -->
    <v-layout my-5>
      <v-flex xs12>
        <router-link to="/post">
          <h2 class="headline my-5 text-xs-center">Post</h2>
        </router-link>
        <PostList :column="$mq==='mobile' ? 1:2"></PostList>
      </v-flex>
    </v-layout>


    <!-- Github -->
    <v-layout my-5>
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">Project</h2>
        <RepositoryList></RepositoryList>
      </v-flex>
    </v-layout>
  </v-container>
</div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'
import PostList from '../components/PostList'
import RepositoryList from '../components/RepositoryList'

export default {
  name: 'HomePage',
  components: {
    ImgBanner,
    PortfolioList,
    PostList,
    RepositoryList
  },
  methods: {
    getImgUrl(img) {
      return require('../assets/' + img)
    }
  },
}
</script>

<style>
.profileImg.mobile {
  display: none;
}

.aboutMe.mobile {
  text-align: center;
  margin: 0 auto;
  font-size: 2vw;
}

.my-5 {
  font-size: 1.7vw;
}
</style>
