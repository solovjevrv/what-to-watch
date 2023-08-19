<template>
  <div class="home">
    <div style="width: 40%; padding: 10%">
      <h1>Login Form</h1>
      <cv-text-input
        style="margin-bottom: 30px"
        name="login"
        v-model="username"
        type="text"
        status="warning"
        size="md"
        label-text="Login"
        helper-text="Login must match email"
      ></cv-text-input>
      <cv-text-input
        style="margin-bottom: 30px"
        name="password"
        v-model="password"
        type="password"
        status="warning"
        size="md"
        label-text="Password"
        helper-text="Do you remember your password?"
      ></cv-text-input>
      <p style="margin-bottom: 30px">
        <a style="color: white; text-decoration: none" href="#"
          >Foggot your password?</a
        >
      </p>
      <cv-button kind="primary" size="md" @click="login()">Sing In</cv-button>
    </div>
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
  data() {
    return {
      username: null,
      password: null,
    };
  },
  methods: {
    login() {
      console.log({
        username: this.username,
        password: this.password,
      });
    },
  },
};
</script>
