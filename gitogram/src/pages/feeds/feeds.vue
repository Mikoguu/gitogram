<template>
  <div class="topline">
    <topline>
      <template #headline>
      <div class="headline">
        <h1 class="headline-title">Gitogram /</h1>
        <ul class="headline-menu">
          <li class="icon">
            <icon name="home"/>
          </li>
          <li class="icon avatar-icon">
            <img src="../../images/Avatar.png" alt="my avatar">
          </li>
          <li class="icon">
            <icon name="exit"/>
          </li>
        </ul>
      </div>
      </template>
      <template #content>
        <ul class="stories">
          <li class="stories-item" v-for="story in stories" :key="story.id">
            <story-user-item 
            :avatar="story.avatar" 
            :username="story.username"
            @onClick="handleClick(story.id)"
            />
          </li>
        </ul>
      </template>
    </topline>
  </div>
  <div class="post" >
    <post>
      <template #post-header>
      <div class="post-header">
        <post-item
        :avatar="getLatestUserAvatar"
        :username="getLatestUsername"
        />
      </div>
      </template>
     <template #post-content>
      <div class="post-content">
        <post-item
        :framework="getLatestUserFramework"
        />
      </div>
     </template>
    </post>
  </div>
</template>

<script>
import { topline } from '../../components/topline'
import { storyUserItem } from '../../components/storyUserItem'
import stories from './storyData.json'
import posts from './postData.json'
import { icon } from '../../icons'
import { post } from '../../components/post'
import { postItem } from '../../components/postItem'

export default {
  name: 'feeds',
  components: {
    topline,
    storyUserItem,
    icon,
    post,
    postItem,
  },
  data() {
    return {
      stories,
      posts
    }
  },
  computed: {
    getLatestUsername() {
      return posts[posts.length - 1].name
    },
    getLatestUserAvatar() {
      return posts[posts.length - 1].avatar
    },
    getLatestUserFramework() {
      return posts[posts.length - 1].framework
    }
  }
}
</script>

<style lang="scss" scoped src="./feeds.scss"></style>