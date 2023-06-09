<template>
  <div class="dev-portal-termsofservice">
    <div
      class="services-top-section flex flex-col items-center justify-center py-16 bg-section_colors-hero"
    >
      <h4 class="services-welcome mb-4 font-normal color-text_colors-secondary text-2xl">
        {{ custom.terms.text }}
      </h4>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TermsOfService',
  components: { },

  setup () {
    return {
    }
  }
})
</script>

<style lang="scss">
.dev-portal-services {
  form {
    display: flex;
    width: 100%;
  }
  .services-top-section {
    border-bottom: 1px solid var(--section_colors-stroke);

    .k-input {
      fill: var(--text_colors-accent);
      border-radius: 3px 0 0 3px !important;
      &::-webkit-input-placeholder { color:var(--text_colors-secondary) !important; }
      &::-moz-placeholder { color:var(--text_colors-secondary) !important; }
      &::-ms-placeholder { color:var(--text_colors-secondary) !important; }
      &::placeholder { color:var(--text_colors-secondary) !important; }
    }
    .k-button {
      border-radius: 0 3px 3px 0;
      font-weight: normal !important;
    }
  }
}
</style>
