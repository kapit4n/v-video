<template>
  <div class="video">
    Hello this is a card
    <v-card contextual-style="dark" :style="{height: 300, margin: '1rem',
        background: 'transparent'}">
      <div slot="body">
        <video
        :style="{width: '300px', height: '200px'}" controls>
        <source :src="url" type="video/mp4">
        </video>
      </div>
      <span slot="header">
        {{title}}
      </span>
      <div slot="footer">
        {{details}}
      </div>
    </v-card>
  </div>
</template>

<script>

import VCard from '@/components/Card.vue';

export default {
  name: 'Video',

  props: {
    url: {
      default: '',
      type: String,
      required: true,
    },
    title: {
      default: '',
      type: String,
      required: true,
    },
    details: {
      default: '',
      type: String,
      required: true,
    },

  },

  components: {
    VCard,
  },
};
</script>
