<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="las la-bars"
          aria-label="Menu"
          @click="toggleSideMenu"
        />

        <q-toolbar-title> Lector QR EFE </q-toolbar-title>

        <div>QR</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="sideMenuOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> MENU </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import { linksList } from "../router/link-list";

import useUI from "../composables/useUI";

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
  },

  setup() {
    const { sideMenuOpen, toggleSideMenu } = useUI();

    return {
      sideMenuOpen,
      toggleSideMenu,
      linksList,
    };
  },
});
</script>
