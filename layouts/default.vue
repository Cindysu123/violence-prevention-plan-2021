<template>
  <client-only>
    <v-app>
      <div style="min-height: 100vh !important">
        <SkipLinks></SkipLinks>
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
