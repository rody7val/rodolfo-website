<template>
  <q-page class="q-pa-md">
    <q-banner rounded class="shadow float-left q-mb-md">
      <template v-slot:avatar>
        <div>
          <q-icon size="46px" name="account_circle" color="primary" /><br>
          <small class="flex flex-center">Resumen</small>
        </div>
      </template>
      <div class="text-body1">
        <div>Emprendedor <span class="text-secondary">✔️</span></div>
        <div>Entusiasta de la tecnología <span class="text-secondary">✔️</span></div>
        <div>En busca de lazos, mercados y soberanía <span class="text-secondary">✔️</span></div>
      </div>
      <q-btn
        class="q-mt-md"
        label="Contacto"
        color="primary"
        icon="contacts"
        to="/contact"
      /><br>
      <q-btn
        class="q-mt-xs"
        label="Curso de vida"
        color="primary"
        icon="picture_as_pdf"
        to="/cv"
      />
    </q-banner>

    <Carousel class="float-right"/>
    <!---->
    <!--
    <q-banner rounded class="shadow float-left q-mb-md">
      <template v-slot:avatar>
        <div>
          <q-icon size="46px" name="corporate_fare" color="primary" /><br>
          <small class="flex flex-center">Negocios</small>
        </div>
      </template>
      <div class="text-body1">
        <div><a href="https://ai.rodolfo.website" class="text-primary">Ágora Informática</a></div>
        <div><a href="#" class="text-primary">Ágora Laboratorios</a></div>
        <div><a href="#" class="text-primary">Fundación Sociedad Agorista</a></div>
      </div>
    </q-banner>
    -->
  </q-page>
</template>

<script>
import { useStore } from 'vuex'
import Carousel from 'components/Carousel.vue'

export default {
  components: { Carousel },
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