<template>
  <v-layout>
    <div :style="{ display: 'flex' }" class="main-container">
      <div class="left-container">
        <div class="header-menu-left-nav">
          <ul class="navbar-nav mr-auto">
            <router-link
              :to="{ name: 'home.index' }"
              active-class="active"
              class="nav-item"
              tag="li"
            >
              <a class="nav-link">Home </a>
            </router-link>
            <router-link
              :to="{ name: 'explore.index' }"
              active-class="active"
              class="nav-item"
              tag="li"
            >
              <a class="nav-link">Explore </a>
            </router-link>
            <router-link
              :to="{ name: 'subscriptions.index' }"
              active-class="active"
              class="nav-item"
              tag="li"
            >
              <a class="nav-link">Subscriptions </a>
            </router-link>
          </ul>
          <span class="navbar-text">
            <a class="btn btn-secondary" href="#" @click.prevent="logout">
              <i class="fa fa-sign-out" />
            </a>
          </span>
        </div>
      </div>
      <div class="center-container" :style="{ background: 'black' }">
        <div
          :style="{
            display: 'flex',
            flexFlow: 'row wrap',
            justifyContent: 'flex-start',
          }"
        >
          <v-video
            v-for="v in videos"
            :key="v.url"
            v-bind:url="v.url"
            v-bind:details="v.details"
            v-bind:title="v.title"
          />
        </div>
      </div>
    </div>
  </v-layout>
</template>

<script>

import VLayout from '@/layouts/Default.vue';
import VVideo from '@/components/Video.vue';

export default {
  name: 'HomeIndex',

  components: {
    VLayout,
    VVideo,
  },

  data() {
    return {
      videos: [
        { url: '/video/video-vue.mp4', title: 'Vue', details: 'Luis Arce' },
        { url: '/video/video-invencible.mp4', title: 'INVENCIBLE', details: 'Luis Arce' },
        { url: '/video/video-vue.mp4', title: 'Vue', details: 'Luis Arce' },
        { url: '/video/video-invencible.mp4', title: 'INVENCIBLE', details: 'Luis Arce' },
        { url: '/video/video-vue.mp4', title: 'Vue', details: 'Luis Arce' },
        { url: '/video/video-invencible.mp4', title: 'INVENCIBLE', details: 'Luis Arce' },
        { url: '/video/video-invencible.mp4', title: 'INVENCIBLE', details: 'Luis Arce' },
        { url: '/video/video-vue.mp4', title: 'Vue', details: 'Luis Arce' },
        { url: '/video/video-vue.mp4', title: 'Vue', details: 'Luis Arce' },
        { url: '/video/video-invencible.mp4', title: 'INVENCIBLE', details: 'Luis Arce' },
      ],
    };
  },
};
</script>
