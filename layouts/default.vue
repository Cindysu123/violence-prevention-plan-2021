<template>
  <client-only>
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
  </client-only>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>
