<template>
  <q-page class="flex column q-pa-md">
    <span class="text-h1">Typography</span>
    <span class="text-h2">Typography</span>
    <span class="text-h3">Typography</span>
    <span class="text-h4">Typography</span>
    <span class="text-h5">Typography</span>
    <q-separator inset />
    <span class="text-body1"
      >Qui et eiusmod irure id anim. Voluptate minim pariatur excepteur id magna
      dolor esse laborum consectetur labore ullamco et. Proident nostrud velit
      aliqua mollit nulla exercitation laborum officia nisi ipsum quis cillum
      nostrud.</span
    >
    <q-btn
      color="primary"
      :label="sideMenuOpen ? 'Cerrar menu lateral' : 'Abrir menu lateral'"
      class="q-mt-md"
      @click="toggleSideMenu"
    ></q-btn>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import useUI from "../composables/useUI";

export default defineComponent({
  name: "TypographyPage",

  setup() {
    const { sideMenuOpen, toggleSideMenu } = useUI();

    return {
      sideMenuOpen,
      toggleSideMenu,
    };
  },
});
</script>
