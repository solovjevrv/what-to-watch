<template>
  <button
    class="c-button"
    :class="[
      kind ? 'c-button--' + kind : '',
      size ? 'c-button--size-' + size : '',
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
  name: 'c-button',
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

<style lang="scss" scoped></style>
