<template>
  <button
    class="cv-button"
    :class="[
      kind ? 'cv-button--' + kind : '',
      size ? 'cv-button--size-' + size : '',
      {'c-button--is-disabled': disabled},
    ]"
    :disabled="disabled"
    :type="nativeType"
    @click="handleClick"
  >
    <span v-if="$slots.default"><slot></slot></span>
  </button>
</template>

<script>
export default {
  name: 'cv-button',
  props: {
    nativeType: {
      type: String,
      default: 'button',
    },
    kind: {
      type: String,
      default: 'primary',
    },
    size: {
      type: String,
      default: 'lg',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleClick(event) {
      this.$emit('click', event);
    },
  },
};
</script>
