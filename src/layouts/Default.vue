<template>
  <div  :style="{width: '100%'}">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark"
        :style="{borderBottom: '1px solid white'}">
      <button
        class="navbar-toggler"
        type="button"
        @click="toggleMenu"
      >
        <span class="navbar-toggler-icon" />
      </button>
      <router-link
        :to="{ name: 'home.index' }"
        class="navbar-brand"
      >
        V-Video
      </router-link>
      <div :style="{display: 'flex', width: '40%'}">
          <input placeholder="Search" :style="{width: '100%', 'max-width': '30rem'}" />
          <button><i class="fa fa-microphone"></i></button>
      </div>
      <div :style="{display: 'flex'}">
        <button class="btn btn-link" :style="{margin: '0 0.5rem'}">
          <i class="fa fa-plus icon-color"></i></button>
        <button class="btn btn-link" :style="{margin: '0 0.5rem'}">
          <i class="fa fa-list icon-color"></i></button>
        <button class="btn btn-link" :style="{margin: '0 0.5rem'}">
          <i class="fa fa-flag icon-color"></i></button>
        <button class="btn btn-link" :style="{margin: '0 0 0 0.5rem'}">
          <i class="fa fa-user icon-color"></i></button>
      </div>
      <div
        :class="{ show : menuCollapsed}"
        class="collapse navbar-collapse header-menu-left-nav"
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
    </nav>

    <div class="">
      <div class="row">
        <div class="col col-12">
          <!-- Content will be placed here -->
          <slot />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* ============
 * Default Layout
 * ============
 *
 * Used for the home and account pages.
 *
 * Layouts are used to store a lot of shared code.
 * This way the app stays clean.
 */

export default {
  /**
   * The name of the layout.
   */
  name: 'DefaultLayout',

  /**
   * The data that can be used by the page.
   *
   * @returns {Object} The view-model data.
   */
  data() {
    return {
      menuCollapsed: false,
    };
  },

  /**
   * The methods that the layout can use.
   */
  methods: {
    /**
     * Will log the user out.
     */
    logout() {
      this.$store.dispatch('auth/logout');
    },

    /**
     * Will toggle the menu.
     */
    toggleMenu() {
      this.menuCollapsed = !this.menuCollapsed;
    },
  },
};
</script>
