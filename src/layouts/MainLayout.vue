<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated >
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title v-html="$store.state.global.title" />

        <q-toggle
          size="lg"
          color="secondary"
          v-model="$store.state.global.dark_mode"
          :icon="$store.state.global.dark_mode ? 'dark_mode' : 'light_mode'"
        />

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      :width="200"
      :breakpoint="400"
      bordered
    >
      <q-scroll-area class="scrollArea">
        <q-list padding>
          <EssentialLink
            v-for="link in essentialLinks"
            :key="link.title"
            v-bind="link"
          />
        </q-list>
      </q-scroll-area>

      <div
        class="absolute-top bg-primary contactSide">
        <div class="absolute-bottom q-pa-md">
          <q-avatar
            size="74px"
            class="q-mb-sm avatarSlide"
          >
            <img src="~assets/avatar.jpg">
          </q-avatar>
          <div class="text-bold">Rodolfo Valguarnera</div>
          <div>admin@rodolfo.website</div>
          <div>(+54)2923699363</div>
        </div>
      </div>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref, computed, watchEffect } from 'vue'
import { useQuasar, setCssVar } from 'quasar'
import { useStore } from 'vuex'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    caption: 'Home',
    title: 'Sobre mí',
    icon: 'landscape',
    to: '/',
    exact: true
  },
  {
    caption: 'CV.pdf',
    title: 'Curso de vida',
    icon: 'description',
    to: '/cv',
    exact: true
  },
  {
    caption: 'Teléfono, redes y correo',
    title: 'Contacto',
    icon: 'phone_iphone',
    to: '/contact',
    exact: true
  },
];

export default {
  components: { EssentialLink },

  setup () {
    const $q = useQuasar()
    const $store = useStore()
    const leftDrawerOpen = ref(false)

    watchEffect(
      () => $q.dark.set($store.state.global.dark_mode),
    )

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
}
</script>

<style lang="css">
  .absolute {
    position: absolute;
  }
  .body--light {
    background-color: #f5f5f5!important;
  }
  .body--dark {
    /*background-color: red!important;*/
  }
  .scrollArea{
    height: calc(100% - 180px);
    margin-top: 180px;
  }
  .contactSide{
    color: white;
    height: 180px;
  }
  .avatarSlide{
    box-shadow: 0 1px 5px #0003, 0 2px 2px #00000024, 0 3px 1px -2px #0000001f;
  }
</style>