<template>
  <v-layout>
    <div :style="{display: 'flex'}" class="main-container">
      <div class="left-container">
        <div
        class="header-menu-left-nav"
      >
        <ul class="navbar-nav mr-auto">
          <span>
            SETTINGS
          </span>
          <router-link
            :to="{ name: 'home.index' }"
            active-class="active"
            class="nav-item"
            tag="li"
          >
            <a class="nav-link">
              Home
            </a>
          </router-link>
          <router-link
            :to="{ name: 'explore.index' }"
            active-class="active"
            class="nav-item"
            tag="li"
          >
            <a class="nav-link">
              Explore
            </a>
          </router-link>
          <router-link
            :to="{ name: 'subscriptions.index' }"
            active-class="active"
            class="nav-item"
            tag="li"
          >
            <a class="nav-link">
              Subscriptions
            </a>
          </router-link>
        </ul>
        <span class="navbar-text">
          <a
            class="btn btn-secondary"
            href="#"
            @click.prevent="logout"
          >
            <i class="fa fa-sign-out" />
          </a>
        </span>
      </div>
      </div>
      <div class="center-container" :style="{background: 'black'}">
        <div :style="{display: 'flex', flexFlow: 'row wrap',
          justifyContent: 'flex-start'}">
          <v-card contextual-style="dark" :style="{height: 300, margin: '1rem',
            background: 'transparent'}">
            <div slot="body">
              <video
              :style="{width: '300px', height: '200px'}" controls>
              <source src="/video/video-invencible.mp4" type="video/mp4">
              </video>
            </div>
            <span slot="header">
              INVENCIBLE
            </span>
            <div slot="footer">
              Skillet 12M vies - 2years ago
            </div>
          </v-card>

          <v-card contextual-style="dark" :style="{height: 300, margin: '1rem',
              background: 'transparent'}">
            <div slot="body">
              <video
              :style="{width: '300px', height: '200px'}" controls>
              <source src="/video-vue.mp4" type="video/mp4">
              </video>
            </div>
            <span slot="header">
              VUE
            </span>
            <div slot="footer">
              Luis Arce 23M views, 20 days ago
            </div>
          </v-card>

        </div>
      </div>
    </div>
  </v-layout>
</template>

<script>
/* ============
 * Home Index Page
 * ============
 *
 * The home index page.
 */

import VLayout from '@/layouts/Default.vue';
import VCard from '@/components/Card.vue';

export default {
  /**
   * The name of the page.
   */
  name: 'HomeIndex',

  /**
   * The components that the page can use.
   */
  components: {
    VLayout,
    VCard,
  },
};
</script>
