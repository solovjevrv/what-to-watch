<template>
  <div class="home">
    <h1>Something Title</h1>
    <div>
      <cv-button kind="primary" @click="func">Button</cv-button>
      <cv-button kind="secondary" @click="func">Button</cv-button>
      <cv-button kind="tertiary" @click="func">Button</cv-button>
      <cv-button kind="ghost" @click="func">Button</cv-button>
      <cv-button kind="danger" @click="func">Button</cv-button>
      <cv-button kind="danger-tertiary" @click="func">Button</cv-button>
      <cv-button kind="danger-ghost" @click="func">Button</cv-button>
    </div>
    <cv-text-input
      inline
      hide-label=""
      placeholder="Input Login here"
    ></cv-text-input>
  </div>
</template>

<script>
import cvButton from '@/components/basic-ui-components/Button.vue';
import cvTextInput from '@/components/basic-ui-components/TextInput.vue';
export default {
  name: 'HomeView',
  components: {
    cvButton,
    cvTextInput,
  },
  methods: {
    func() {
      console.log('Event!');
    },
  },
};
</script>
