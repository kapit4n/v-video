<template>
  <v-layout>
    <div :style="{display: 'flex'}" class="main-container">
      <div class="left-container">
        <div
        class="header-menu-left-nav"
      >
        <ul class="navbar-nav mr-auto">
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
      <div class="center-container">
        center side bar
        <v-card contextual-style="dark">
          <span slot="header">
            {{ $t('general.welcome') }}
          </span>
          <div slot="body">
            <p>
              Get started with the Vue 2 boilerplate
            </p>
            <p>
              For questions, contact me:
            </p>
            <p>
              <a
                class="btn btn-outline-primary"
                href="http://gitter.im/petervmeijgaard"
                target="_blank"
              >
                <i
                  class="fa fa-github fa-fw"
                  aria-hidden="true"
                />
                <span class="pl-2">
                  Gitter
                </span>
              </a>
              <a
                class="btn btn-outline-primary"
                href="http://github.com/petervmeijgaard"
                target="_blank"
              >
                <i
                  class="fa fa-github fa-fw"
                  aria-hidden="true"
                />
                <span class="pl-2">
                  GitHub
                </span>
              </a>
              <a
                class="btn btn-outline-primary"
                href="http://twitter.com/petervmeijgaard"
                target="_blank"
              >
                <i
                  class="fa fa-twitter fa-fw"
                  aria-hidden="true"
                />
                <span class="pl-2">
                  Twitter
                </span>
              </a>
            </p>
            <p>
              For bugs, see:
            </p>
            <a
              class="btn btn-outline-primary"
              href="https://github.com/petervmeijgaard/vue-2.0-boilerplate/issues"
              target="_blank"
            >
              <i
                class="fa fa-github fa-fw"
                aria-hidden="true"
              />
              <span class="pl-2">
                GitHub
              </span>
            </a>
          </div>
          <div slot="footer">
            Made with love by Vivid Web
          </div>
        </v-card>
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
