<template>
  <van-button
    tag="a"
    :href="url"
    class="van-goods-action__big-btn"
    :type="primary ? 'primary' : 'default'"
    bottom-action
    @click="onClick"
  >
    <slot>{{ text }}</slot>
  </van-button>
</template>

<script>
import { create } from '../utils';
import VanButton from '../button';
import RouterLink from '../mixins/router-link';

export default create({
  name: 'goods-action-big-btn',

  mixins: [RouterLink],

  components: {
    VanButton
  },

  props: {
    url: String,
    text: String,
    primary: Boolean
  },

  methods: {
    onClick(event) {
      this.$emit('click', event);
      this.routerLink();
    }
  }
});
</script>
