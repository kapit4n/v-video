<template>
  <div class="card">
    <div
      v-if="hasSlot('body')"
      class="card-body"
    >
      <slot name="body" />
    </div>
     <h4
      v-if="hasSlot('header')"
      :class="classNamesHeader"
      :style="{background: 'transparent !important'}"
    >
      <slot name="header" />
    </h4>
    <div
      v-if="hasSlot('footer')"
      class="card-footer"
      :style="{background: 'transparent', color: '#d9dbde'}"
    >
      <slot name="footer" />
    </div>
  </div>
</template>

<script>

import SlotMixin from '@/mixins/slot';

export default {
  name: 'Card',

  mixins: [
    SlotMixin,
  ],

  props: {
    contextualStyle: {
      default: 'primary',
      type: String,
      required: false,
    },
  },

  computed: {
    classNamesHeader() {
      const classNames = ['card-header'];

      if (this.contextualStyle) {
        classNames.push(`bg-${this.contextualStyle}`);
        classNames.push('text-white');
      } else {
        classNames.push('bg-default');
      }

      return classNames;
    },
  },
};
</script>
