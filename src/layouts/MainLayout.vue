<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-grey-2" bordered>
      <q-toolbar class="flex justify-between">
        <q-btn
          class="bg-grey-6"
          flat
          dense
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer()"
        />

<!--        <q-toolbar-title> Quasar App </q-toolbar-title>-->

<!--        <div class="flex q-gutter-sm">-->
<!--          <div>Quasar v{{ $q.version }}</div>-->
<!--          <div>Quasar v{{ $q.version }}</div>-->
<!--        </div>-->

        <q-item clickable v-ripple>
          <q-item-section>
            <q-item-label class="text-grey-8 text-weight-medium">Фамиля Имя</q-item-label>
            <q-item-label class="text-grey-7 text-weight-medium" caption>Администратор</q-item-label>
          </q-item-section>
          <q-item-section side>
            <q-avatar size="48px">
              <img src="https://cdn.quasar.dev/img/avatar.png" />
            </q-avatar>
          </q-item-section>
        </q-item>
      </q-toolbar>
    </q-header>

    <q-drawer
      class="bg-grey-9"
      show-if-above
      bordered
      :mini="miniState"
    >
      <q-list class="q-pt-xxl">
<!--        <q-item-label header> Essential Links </q-item-label>-->

<!--        <EssentialLink-->
<!--          v-for="link in essentialLinks"-->
<!--          :key="link.title"-->
<!--          v-bind="link"-->
<!--        />-->
        <AsideMenu></AsideMenu>
      </q-list>
    </q-drawer>

    <q-page-container class="bg-grey-4">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import AsideMenu from "components/AsideMenu.vue";

const linksList = [
  {
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    AsideMenu,
  },

  setup() {
    const miniState = ref(true);

    return {
      essentialLinks: linksList,
      miniState,
      toggleLeftDrawer() {
        this.miniState = !this.miniState
      },
    };
  },
});
</script>

<style>

  .q-drawer--standard {
    transition-duration: 0.2s;
  }
  .q-drawer--mini {
    transition-duration: 0.2s;
  }
  .q-header {
    transition-duration: 0.2s;
  }

</style>
