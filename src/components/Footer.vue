<template>
  <header
    id="site-footer"
    class="flex items-center fixed w-full bottom-0 z-10"
  >
    <div class="w-100 container max-w-screen-2xl mx-auto flex justify-between items-center px-5 md:px-0">
      <a
        href="https://konghq.com"
        target="_blank"
      >
        Kong, Inc.
      </a>
      <nav class="flex items-center links">
        <router-link
          data-testid="tos-link"
          :to="{ name: 'TermsOfService' }"
          class="mr-2 p-2 tos-link"
        >
          <div class="background-color-wrapper" />
          Terms of Service
        </router-link>
        <router-link
          data-testid="privacy-link"
          :to="{ name: 'PrivacyPolicy' }"
          class="mr-2 p-2 privacy-link"
        >
          <div class="background-color-wrapper" />
          Privacy Policy
        </router-link>
      </nav>
    </div>
  </header>
</template>

<script>
import { defineComponent } from 'vue'
import { mapState, storeToRefs } from 'pinia'
import { useAppStore } from '@/stores'
import { portalApi } from '@/services'

export default defineComponent({
  name: 'Footer',
  components: { },
  setup () {
    const appStore = useAppStore()
    const { globalLoading } = storeToRefs(appStore)

    const logout = async () => {
      globalLoading.value = true

      const logoutUrl = await appStore.logout()

      window.location.href = logoutUrl
    }

    const logoSrc = portalApi.getApiLink('/portal_assets/logo')

    return {
      logout,
      logoSrc
    }
  },

  computed: {
    ...mapState(useAppStore, {
      developer: store => store.developerSession.data?.developer,
      isPublic: 'isPublic'
    })
  }

})
</script>

<style lang="scss" scoped>
.logo {
  max-height: 41px;
}

#site-footer {
  height: var(--headerHeight);
  background-color: var(--section_colors-header);
  border-bottom: 1px solid var(--section_colors-stroke);
  margin-top: 100px;

  .links a {
    color: var(--text_colors-header);
    &:hover{
      backdrop-filter: brightness(1.35);
    }
  }
}
</style>
