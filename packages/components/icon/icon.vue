<template>
  <i
    class="c-icon"
    :class="[
      `icon-${name}`,
      type ? `c-icon__${type}` : '',
      {
        'c-icon__background': backgroundColor
      }
    ]"
    :style="{
      width: size,
      height: size,
      fontSize: size,
      backgroundColor,
      color,
      borderRadius
    }"
    @click="onClick">
  </i>
</template>

<script>
import to from '../../utils/to'

export default {
  name: 'cIcon',
  props: {
    name: {
      type: String,
      default: '',
      required: true
    },
    type: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: ''
    },
    backgroundColor: {
      type: String,
      default: ''
    },
    size: {
      type: String,
      default: ''
    },
    borderRadius: {
      type: String
    },
    to: {
      type: [String, Object],
      default: null
    }
  },
  methods: {
    onClick () {
      to({
        vm: this,
        to: this.to
      })
    }
  }
}
</script>
