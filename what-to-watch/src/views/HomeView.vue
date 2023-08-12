<template>
  <div class="home">
    <h1>Something Title</h1>
    <c-button kind="primary" @click="func">Button</c-button>
    <c-button kind="secondary" @click="func">Button</c-button>
    <c-button kind="tertiary" @click="func">Button</c-button>
    <c-button kind="ghost" @click="func">Button</c-button>
    <c-button kind="danger" @click="func">Button</c-button>
    <c-button kind="danger-tertiary" @click="func">Button</c-button>
    <c-button kind="danger-ghost" @click="func">Button</c-button>
  </div>
</template>

<script>
import cButton from '@/components/basic-ui-components/Button.vue';
export default {
  name: 'HomeView',
  components: {
    cButton,
  },
  methods: {
    func() {
      console.log('Event!');
    },
  },
};
</script>
