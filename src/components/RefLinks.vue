<template>
  <div>
      <slot :links="links"></slot>
  </div>
</template>

<script>
import { defineComponent, reactive } from "vue";

export default defineComponent({
  name: "RefLinks",
  setup() {
    const links =
      reactive({
        'installed': {
          title: "Installed CLI Plugins",
          list: [
            {
              href: "https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel",
              text: "babel",
            },
            {
              href: "https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-typescript",
              text: "typescript",
            }
          ]
        },
        'essential': {
          title: "Essential Links",
          list: [
            { href: "https://vuejs.org", text: "Core Docs" },
            { href: "https://forum.vuejs.org", text: "Forum" },
            { href: "https://chat.vuejs.org", text: "Community Chat" },
            { href: "https://twitter.com/vuejs", text: "Twitter" },
            { href: "https://news.vuejs.org", text: "News" }
          ]
        },
        'ecosyste': {
          title: "Ecosystem",
          list: [
            { href: "https://router.vuejs.org", text: "vue-router" },
            { href: "https://vuex.vuejs.org", text: "vuex" },
            {
              href: "https://github.com/vuejs/vue-devtools#vue-devtools",
              text: "vue-devtools",
            },
            { href: "https://vue-loader.vuejs.org", text: "vue-loader" },
            {
              href: "https://github.com/vuejs/awesome-vue",
              text: "awesome-vue",
            },
          ]
        }
      })
    return { links }
  },
});
</script>
