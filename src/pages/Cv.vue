<template>
  <q-page class="q-pa-md">
    <!--contacto-->
    <div class="text-h6">Contacto</div>
    <ul class="q-mt-none">
      <li>ruthwolf@protonmail.com</li>
      <li>(+54)2923699363</li>
      <li>rodolfo.website</li>
    </ul>

    <!--profesión-->
    <div class="text-h6">‍Profesiones</div>
    <p class="q-ml-lg">Técnico Informático, Desarrollador JavaScript e Ingeniero DevOps.</p>

    <!--estudios-->
    <div class="text-h6">‍Estudios</div>
    <q-table
      :columns="columns"
      :rows="rows"
      row-key="name"
    />

    <!--descarga-->
    <q-btn
      class="q-mt-md"
      label="Descargar"
      color="primary"
      icon-right="file_download"
      href="http://cloud.rodolfo.website/s/8y6KXxny2KSxrw2/download/CV%20-%20Rodolfo%20Valguarnera.pdf"
      rel="noopener noreferrer"
      target="_blank"
    />
  </q-page>
</template>

<script>
import { ref } from "vue"
import { useStore } from 'vuex'

export default {
  mounted(){
    const $store = useStore()
    $store.commit('global/setTitle', '<span class="text-secondary">📄</span> Curso de vida')
  },
  setup () {
    const columns = ref([{
      name: 'name',
      required: true,
      label: 'Carrera',
      align: 'left',
      field: row => row.name,
      format: val => `${val}`,
      sortable: true
    },{
      name: 'date',
      label: 'Fecha',
      align: 'center',
      field: row => row.date,
      sortable: true
    },{
      name: 'uni',
      label: 'Entidad',
      align: 'left',
      field: row => row.uni,
      sortable: true
    },{
      name: 'type',
      label: 'Nivel',
      align: 'left',
      field: row => row.type,
      sortable: true
    },{
      name: 'from',
      label: 'Lugar',
      align: 'left',
      field: row => row.from,
      sortable: true
    }])

    const rows = ref([{
      name: 'Emprendimientos Informáticos',
      date: '01-02-2013 / 01-02-2016',
      uni: 'Universidad Provincial Del Sudoeste',
      type: 'Universitario',
      from: 'Pigüé, Buenos Aires, Argentina'
    }])

    return { columns, rows }
  }
}
</script>