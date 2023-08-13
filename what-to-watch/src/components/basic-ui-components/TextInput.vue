<template>
  <div class="cv-text-input" :class="{'cv-text-input--is-inline': inline}">
    <label v-if="!hideLabel" class="cv-text-input__label" for="name">{{
      labelText
    }}</label>
    <input
      class="cv-text-input__field"
      :placeholder="placeholder"
      type="text"
      id=""
      name="name"
    />
    <span class="cv-text-input__helper-text">{{ helperText }}</span>
  </div>
</template>

<script>
export default {
  name: 'cv-text-input',
  props: {
    name: {
      type: String,
    },
    labelText: {
      type: String,
      default: 'Label',
    },
    hideLabel: {
      type: Boolean,
      default: false,
    },
    inline: {
      type: Boolean,
      default: false,
    },
    helperText: {
      type: String,
      default: '',
    },
    placeholder: {
      type: String,
      default: '',
    },
  },
};
</script>
