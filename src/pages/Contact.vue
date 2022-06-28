<template>
  <q-page class="q-pa-md">
    <!--contacto-->
    <q-banner rounded class="bg-secondary text-dark">
        <div class="row">
          <div class="personal col-12 col-sm-4">
            <div class="text-overline text-grey-8">Personal</div>
            <!--telefono-->
            <q-btn
              flat
              dense
              label="(+54)2923699363"
              icon="phone_android"
              color="primary"
              href="tel:+542923699363"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="llamada"
              >
                llamada
              </q-tooltip>
            </q-btn>
            <br/>
            <!--whatsapp-->
            <q-btn
              flat
              dense
              color="primary"
              href="https://wa.me/542923699363"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-img
                src="~assets/whatsapp-logo.svg"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="pointer text-lowercase">(+54)2923699363</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="whatsapp"
              >
                whatsapp
              </q-tooltip>
            </q-btn>
            <br/>
            <!--telegram-->
            <q-btn
              flat
              dense
              color="primary"
              href="tg://resolve?domian=rvalguarnera"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-img
                src="~assets/telegram-logo.svg"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="pointer text-lowercase">@rvalguarnera</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="telegram"
              >
                telegram
              </q-tooltip>
            </q-btn>
            <br/>
            <!--instagram-->
            <q-btn
              flat
              dense
              color="primary"
              href="https://www.instagram.com/r.valguarnera/"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-img
                src="~assets/instagram-logo.png"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="pointer text-lowercase">@rvalguarnera</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="instagram"
              >
                instagram
              </q-tooltip>
            </q-btn>
            <br/>
          </div>
          <div class="negocios col-12 col-sm">
            <div class="text-overline text-grey-8">Trabajo</div>
            <!--correo-->
            <q-btn
              flat
              dense
              color="primary"
              href="mailto:ruthwolf@protonmail.com"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-img
                src="~assets/mail-logo.svg"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="pointer text-lowercase">ruthwolf@protonmail.com</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="correo"
              >
                correo
              </q-tooltip>
            </q-btn>
            <br/>
            <!--linkedin-->
            <q-btn
              flat
              dense
              color="primary"
              href="https://www.linkedin.com/in/rvalguarnera/"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-img
                src="~assets/linkedin-logo.svg"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="pointer text-lowercase">@rvalguarnera</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="linkedin"
              >
                linkedin
              </q-tooltip>
            </q-btn>
            <br/>
            <!--github-->
            <q-btn
              flat
              dense
              color="primary"
              href="https://github.com/rody7val"
              rel="noopener noreferrer"
              target="_blank"
            >
              <q-img
                src="~assets/github-logo.svg"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="pointer text-lowercase">@rody7val</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="github"
              >
                github
              </q-tooltip>
            </q-btn>
            <br/>
          </div>
          <div class="privacidad col-12 col-sm-3">
            <div class="text-overline text-grey-8">Privacidad</div>
            <!--surespot-->
            <q-btn
              flat
              dense
              color="primary"
              target="_blank"
              rel="noopener noreferrer"
              @click="surespot = !surespot" 
            >
              <q-img
                src="~assets/surespot-logo.png"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="text-lowercase">th0t</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="surespot"
              >
                surespot
              </q-tooltip>
            </q-btn>
            <br/>
            <!--nearpeer-->
            <q-btn
              flat
              dense
              color="primary"
              target="_blank"
              rel="noopener noreferrer"
              @click="nearpeer = !nearpeer" 
            >
              <q-img
                src="~assets/nearpeer-logo.png"
                style="width: 25px"
                class="q-mr-sm"
              />
              <label class="text-lowercase">hathor</label>
              <q-tooltip
                anchor="center right"
                self="center left"
                v-model="nearpeer"
              >
                nearpeer
              </q-tooltip>
            </q-btn>
            <br/>
          </div>
        </div>

      <div class="row">
        <div class="col">
          <div class="text-body1 text-center q-my-md">Estamos en contacto 👋</div>
        </div>
      </div>

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
import { ref } from 'vue'
import { useStore } from 'vuex'

export default {
  mounted () {
    const $store = useStore()
    $store.commit('global/setTitle', '<span class="text-secondary">📱</span> Contacto')
  },
  setup () {
    return {
      llamada: ref(false),
      whatsapp: ref(false),
      telegram: ref(false),
      correo: ref(false),
      instagram: ref(false),
      linkedin: ref(false),
      github: ref(false),
      surespot: ref(false),
      nearpeer: ref(false),
    }
  }
}
</script>

<style lang="css">
.pointer {
  cursor: pointer!important;
}
</style>

