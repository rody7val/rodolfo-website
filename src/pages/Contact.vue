<template>
  <q-page class="q-pa-md">
    <!--contacto-->
    <q-banner rounded class="bg-secondary text-dark">

      <div class="text-body1">
        Estamos en contacto 👋 ...
      </div>

      <template v-slot:avatar>
        <div class="text-body1">
          <!--telefono-->
          <q-btn
            flat
            color="primary"
            href="https://wa.me/542923464050"
            rel="noopener noreferrer"
            target="_blank"
          >
            <q-img
              src="~assets/whatsapp-logo.png"
              style="width: 20px"
              class="q-mr-sm"
            />
            <label>(+54)2923699363</label>
          </q-btn><br/>

          <!--linkedin-->
          <q-btn
            flat
            color="primary"
            href="https://www.linkedin.com/in/rvalguarnera/"
            rel="noopener noreferrer"
            target="_blank"
          >
            <q-img
              src="~assets/linkedin-logo.svg"
              style="width: 20px"
              class="q-mr-sm"
            />
            <label>@rvalguarnera</label>
          </q-btn><br/>

          <!--github-->
          <q-btn
            flat
            color="primary"
            href="https://github.com/rody7val"
            rel="noopener noreferrer"
            target="_blank"
          >
            <q-img
              src="~assets/github-logo.svg"
              style="width: 20px"
              class="q-mr-sm"
            />
            <label>@rody7val</label>
          </q-btn><br/>

          <!--instagram-->
          <q-btn
            flat
            color="primary"
            href="https://www.instagram.com/r.valguarnera/"
            rel="noopener noreferrer"
            target="_blank"
          >
            <q-img
              src="~assets/instagram-logo.png"
              style="width: 20px"
              class="q-mr-sm"
            />
            <label>@rvalguarnera</label>
          </q-btn><br/>

          <!--correo-->
          <q-btn
            flat
            color="primary"
            href="mailto:admin@rodolfo.website"
            rel="noopener noreferrer"
            target="_blank"
          >
            <q-img
              src="~assets/mail-logo.svg"
              style="width: 25px"
              class="q-mr-sm"
            />
            <label>admin@rodolfo.website</label>
          </q-btn><br/>
        </div>
      </template>

      <template v-slot:action>
        <q-btn
          class="q-mt-md"
          label="Curso de vida"
          color="primary"
          icon-right="picture_as_pdf"
          to="/cv"
        />
        <q-btn
          class="q-mt-md"
          label="Sobre mi"
          color="primary"
          icon-right="landscape"
          to="/"
        />
      </template>
    </q-banner>
  </q-page>
</template>

<script>
import { useStore } from 'vuex'
//import logo from '../assets/linkedin-logo.svg'

export default {
  mounted () {
    const $store = useStore()
    $store.commit('global/setTitle', '<span class="text-secondary">📱</span> Contacto')
  },

}
</script>

