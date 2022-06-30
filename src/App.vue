<script>
  import { ref } from 'vue'
  import { Authenticator } from '@aws-amplify/ui-vue';
  import '@aws-amplify/ui-vue/styles.css';
  import './assets/amplify.css'

  export default {
    components: {
      Authenticator
    },
    setup() {
      const configurationOptions = ref({
        signInConfig: {
          isSignUpDisplayed: false
        }
      })

      return { configurationOptions }
    }
  }
</script>

<template>
  <Authenticator
    :form-fields="formFields"
    :hide-sign-up="true"
  >
    <template v-slot:header>
      <div style="padding: var(--amplify-space-large); text-align: center">
        <img
          class="amplify-image"
          alt="Amplify logo"
          src="https://docs.amplify.aws/assets/logo-dark.svg"
        />
      </div>
    </template>

    <template v-slot:sign-in-header>
      <h3
        class="amplify-heading"
        style="padding: var(--amplify-space-xl) 0 0 var(--amplify-space-xl)"
      >
        Sign in to your account
      </h3>
    </template>

    <template v-slot:sign-in-footer>
      <div style="text-align: center">
        <button
          @click="toResetPassword"
          class="amplify-button amplify-field-group__control"
          data-fullwidth="false"
          data-size="small"
          data-variation="link"
          type="button"
          style="font-weight: normal"
        >
          Reset Password
        </button>
      </div>
    </template>

    <template v-slot:footer>
      <div style="padding: var(--amplify-space-large); text-align: center">
        <p class="amplify-text" style="color: var(--amplify-colors-neutral-80)">
          © All Rights Reserved
        </p>
      </div>
    </template>

    <template v-slot:confirm-sign-up-header>
      <h3
        class="amplify-heading"
        style="padding: var(--amplify-space-xl) 0 0 var(--amplify-space-xl)"
      >
        Enter Information:
      </h3>
    </template>

    <template v-slot:confirm-sign-up-footer>
      <div>Footer Information</div>
    </template>

    <template v-slot:setup-totp-header>
      <h3
        class="amplify-heading"
        style="padding: var(--amplify-space-xl) 0 0 var(--amplify-space-xl)"
      >
        Enter Information:
      </h3>
    </template>

    <template v-slot:setup-totp-footer>
      <div>Footer Information</div>
    </template>

    <template v-slot:confirm-sign-in-header>
      <h3
        class="amplify-heading"
        style="padding: var(--amplify-space-xl) 0 0 var(--amplify-space-xl)"
      >
        Enter Information:
      </h3>
    </template>

    <template v-slot:confirm-sign-in-footer>
      <div>Footer Information</div>
    </template>

    <template v-slot:reset-password-header>
      <h3
        class="amplify-heading"
        style="padding: var(--amplify-space-xl) 0 0 var(--amplify-space-xl)"
      >
        Enter Information:
      </h3>
    </template>

    <template v-slot:reset-password-footer>
      <div>Footer Information</div>
    </template>

    <template v-slot:confirm-reset-password-header>
      <h3
        class="amplify-heading"
        style="padding: var(--amplify-space-xl) 0 0 var(--amplify-space-xl)"
      >
        Enter Information:
      </h3>
    </template>

    <template v-slot:confirm-reset-password-footer>
      <div>Footer Information</div>
    </template>

    <template v-slot="{ user, signOut }">
      <h1>Hello {{ user.username }}!</h1>
      <button @click="signOut">Sign Out</button>
    </template>
  </Authenticator>
</template>
