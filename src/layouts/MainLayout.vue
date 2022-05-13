<template>
  <div class="constrained bg-grey-2">
    <q-layout view="hHh lpR fFf">
      <!--// Header //-->
      <q-header class="bg-white text-dark">
        <q-toolbar>
          <q-toolbar-title>
            <q-avatar>
              <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
            </q-avatar>
            <span @click="$router.push({ name: 'Home' })">Web App</span>
          </q-toolbar-title>

        </q-toolbar>
      </q-header>

      <!--// Left drawer //-->
      <q-drawer
          show-if-above
          v-model="rightDrawerOpen"
          @before-hide="rightDrawerOpen = false"
          :width="320"
          side="right"
          class="bg-grey-2 q-pa-lg"
      >
        Right Menu
      </q-drawer>

      <!--// Main content //-->
      <q-page-container class="bg-grey-2">
        <router-view/>
      </q-page-container>
    </q-layout>
  </div>
</template>

<script setup lang="ts">
import {ref} from 'vue';

const rightDrawerOpen = ref(true);
</script>

<style type="text/css">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;300&display=swap");

.constrained {
  width: 100%;
  height: 100%;
}

.constrained .q-layout,
.constrained .q-header,
.constrained .q-footer {
  margin: 0 auto;
  /* max-width: 1245px !important; */
}

.nav-btn {
  min-width: 90px;
}
</style>
