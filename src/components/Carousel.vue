<template>
  <div style="max-width: 380px; width: 100%;">
    <q-carousel
      swipeable
      animated
      arrows
      v-model="slide"
      v-model:fullscreen="fullscreen"
      infinite
      control-color="secondary"
    >
      <!--
      <q-carousel-slide :name="1" img-src="~assets/_1.jpg" />
      -->
      <q-carousel-slide :name="1" img-src="~assets/_2.jpg" />
      <q-carousel-slide :name="2" img-src="~assets/_3.jpg" />
      <q-carousel-slide :name="3" img-src="~assets/_4.webp" />

      <template v-slot:control>
        <q-carousel-control
          position="bottom-right"
          :offset="[18, 18]"
        >
          <q-btn
            push round dense color="primary" text-color="secondary"
            :icon="fullscreen ? 'fullscreen_exit' : 'fullscreen'"
            @click="fullscreen = !fullscreen"
          />
        </q-carousel-control>
      </template>
    </q-carousel>
    <div class="text-center"><i>Imágenes que inspiran</i></div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      slide: ref(1),
      fullscreen: ref(false)
    }
  }
}
</script>
