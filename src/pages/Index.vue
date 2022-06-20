<template>
  <q-page class="q-pa-md">
    <ul class="text-body1 q-mt-none">
      <li>Emprendedor</li>
      <li>Entusiasta de la tecnología</li>
      <li>En busca de lazos, mercaderes y alianzas</li>
      <!--
      <li>CEO y Fundador de <a href="#" class="text-primary">Fundación Sociedad Agorista</a></li>
      <li>CEO y Fundador <a href="#" class="text-primary">Hathor Informática</a></li>
      <li>CEO y Fundador <a href="#" class="text-primary">Thot Laboratorios</a></li>
      -->
    </ul>
  </q-page>
</template>

<script>
import { useStore } from 'vuex'

export default {
  mounted(){
    const $store = useStore()
    $store.commit('global/setTitle', '<span class="text-secondary">🗻</span> Sobre mí')
  },
  //( ☀ 🐍 🦅)
  //beforeUnmount(){
    //const $store = useStore()
    //$store.commit('setTitle', )
  //},
}
</script>