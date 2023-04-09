<script setup lang="ts">
const alpine = useAppConfig().alpine;

defineProps({
  padded: {
    type: Boolean,
    default: true,
  },
});

useHead({
  htmlAttributes: {
    lang: "en",
  },
  meta: [{ name: "twitter:card", content: "summary_large_image" }],
  link: [
    {
      rel: "icon",
      type: "image/x-icon",
      href: "/favicon.ico",
    },
    {
      rel: "icon",
      type: "image/png",
      href: "/favicon.png",
    },
  ],
});

useContentHead(alpine as any);
</script>

<template>
  <Container class="app-layout">
    <AppLoadingBar />
    <AppHeader v-if="alpine.header" />
    <slot />
    <AppFooter v-if="alpine.footer" />
  </Container>
</template>

<style lang="ts" scoped>
css({
  '.app-layout': {
    minWidth: '{size.xs}'
  }
})
</style>
