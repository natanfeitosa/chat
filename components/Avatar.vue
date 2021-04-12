<template>
  <button
    type="button"
    class="btn btn-secondary border rounded-circle"
    :style="style"
    @click="$emit('click', $event)"
    @mouseover="$emit('mouseover', $event)"
    @mouseout="$emit('mouseout', $event)"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'Avatar',
  // data() {
  //   return {
  //     style: `width:${size}; height:${size}; background-position:center; background-size:cover; background-image:url("${src}")`
  //   }
  // },
  props: {
    size: { type: String, default: '' },
    src: { type: String, default: '170px' },
  },
  computed: {
    style() {
      return `width:${this.size}; height:${this.size}; background-position:center; background-size:cover; background-image:url("${this.src}")`
    },
  },
}
</script>
