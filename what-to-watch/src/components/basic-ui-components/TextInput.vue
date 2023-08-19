<template>
  <div
    class="cv-text-input"
    :class="[
      `cv-text-input--${status}`,
      `cv-text-input--${size}`,
      {'cv-text-input--is-inline': inline},
      {'cv-text-input--readonly': readonly},
    ]"
  >
    <label v-if="!hideLabel" class="cv-text-input__label" :for="name">{{
      labelText
    }}</label>
    <div class="cv-text-input__wrapper">
      <input
        class="cv-text-input__field"
        :placeholder="placeholder"
        :type="naviteType"
        :id="id"
        :name="name"
        :disabled="readonly"
        :value="value"
        @input="handleInput"
        @change="handleChange"
      />
      <div class="cv-text-input__interactive-block">
        <cv-status-icon :type="status"></cv-status-icon>
        <button
          v-show="type == 'password'"
          class="cv-text-input__toggle-password"
          type="button"
          :disabled="readonly"
          @click="togglePasswordView()"
        >
          <i
            :class="
              naviteType == 'password' ? 'cv-icon-view' : 'cv-icon-view-off'
            "
          ></i>
        </button>
      </div>
    </div>
    <span class="cv-text-input__helper-text">{{ helperText }}</span>
  </div>
</template>

<script>
import cvStatusIcon from '@/components/basic-ui-components/StatusIcon.vue';
export default {
  components: {
    cvStatusIcon,
  },
  name: 'cv-text-input',
  props: {
    value: {
      required: true,
    },
    id: {
      type: String,
    },
    name: {
      type: String,
    },
    type: {
      type: String,
      default: 'text',
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
    status: {
      type: String,
      default: 'default',
    },
    readonly: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: 'md',
    },
  },
  data() {
    return {
      naviteType: 'text',
    };
  },
  methods: {
    handleInput(event) {
      this.$emit('input', event.target.value);
    },
    handleChange(event) {
      this.$emit('change', event.target.value);
    },
    togglePasswordView() {
      this.naviteType = this.naviteType == 'text' ? 'password' : 'text';
    },
  },
  mounted() {
    this.naviteType = this.type;
  },
  watch: {
    type(val) {
      this.naviteType = val;
    },
  },
};
</script>
