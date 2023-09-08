<template>
  <div />
</template>

<script>

export default {
  name: 'PrivacyPolicy',
  components: {
  },
  props: {

  },
  emits: [],
  setup () {
  },
  data () {
    // return {
    //   activeView: 'grid'
    // }
  },
  computed: {
    // disabled () {
    //   return this.services.length === 0 ? true : null
    // }
  },
  mounted () {
    // const activeView = localStorage.getItem('portal-catalog-view') || 'grid'

    // this.setActiveView(activeView)
  },
  methods: {
    // setActiveView (val) {
    //   this.activeView = val
    //   localStorage.setItem('portal-catalog-view', val)
    //   this.$emit('active-view-changed', val)
    // }
  }
}
</script>

<style lang="scss" scoped>
.services-content {
  --grey-500: var(--button_colors-primary-fill);

  .services-label {
    color: var(--text_colors-primary);
    font-size: var(--type-xl);
    font-weight: normal;
  }

  .view-switch-button {
    --grey-500: var(--text_colors-primary);
    --spacing-xs: 6px;
    --spacing-md: 6px;
    --KButtonOutlineBase: var(--section_colors-body);
    --KButtonOutlineBorder: var(--text_colors-primary);
    --KButtonOutlineHover: var(--section_colors-tertiary);

    border: 1px solid var(--KButtonOutlineBorder) !important;
  }
}

.serv-catalog-empty-state {
  margin: auto;
  width: 20rem;
  display: block;
  margin-top: 80px;
}

.serv-catalog-loading-spinner {
  width: 100%;
  display: flex;
  justify-content: center;
}

.serv-catalog-no-services {
  text-align: center;
  padding: 20px var(--spacing-xs);
}
</style>
