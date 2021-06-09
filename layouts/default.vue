<template>
  <client-only>
    <v-app>
      <div id="base">
        <SkipLinks></SkipLinks>
        <AppNav></AppNav>
        <AppSidebar></AppSidebar>
        <ModalGoals></ModalGoals>
        <main>
          <nuxt id="main" class="" />
        </main>
      </div>
      <AppFooter></AppFooter>
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

<style>
#base {
  min-height: 100vh !important;
}
</style>
