<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated class="bg-green-6">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
            Mon tuto - quasar et animation gsap
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      :width=200
    >
      <q-list>
        <q-item-label
          header
        >
          <div class="text-center">Bonjour</div>
        </q-item-label>

        <q-item clickable v-ripple :to="{name: 'home'}">
          <q-item-section avatar>
            <q-avatar color="teal" text-color="white" icon="home" />
          </q-item-section>

          <q-item-section>Home</q-item-section>
        </q-item>

        <q-item clickable v-ripple :to="{name: 'calculatrice'}">
          <q-item-section avatar>
            <q-avatar color="teal" text-color="white" icon="fa-solid fa-calculator" />
          </q-item-section>

          <q-item-section>Calculatrice</q-item-section>
        </q-item>

      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'



export default defineComponent({
  name: 'MainLayout',

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
