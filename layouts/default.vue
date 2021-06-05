<template>
  <no-ssr>
    <!-- <SkipLinks></SkipLinks> -->
    <v-app>
      <div style="min-height: 100vh !important">
        <AppNav></AppNav>
        <AppSidebar></AppSidebar>
        <main>
          <nuxt id="main" class="" />
        </main>
      </div>
      <!-- <AppFooter></AppFooter> -->
    </v-app>
  </no-ssr>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>
