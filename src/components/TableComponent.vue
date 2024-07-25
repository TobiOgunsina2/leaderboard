<script setup lang="jsx">
import 'ag-grid-community/styles/ag-grid.css'
import 'ag-grid-community/styles/ag-theme-quartz.css'
import { AgGridVue } from 'ag-grid-vue3'
import { onMounted, ref } from 'vue'
import ButtonComponent from './ButtonComponent.vue'
import StatusComponent from './StatusComponent.vue'

const golfData = ref([])

const emit = defineEmits(['togglePopUp'])

onMounted(() => {
  fetch('http://localhost:3000/players')
    .then((res) => {
      return res.json()
    })
    .then((data) => {
      golfData.value = data
    })
    .catch(() => {})
})

const rowData = golfData

// Column Definitions: Defines the columns to be displayed.
const colDefs = ref([
  {
    field: 'POS',
    flex: 1,
    filter: false,
    valueGetter: (p) => p.node.rowIndex + 1
  },
  { field: 'player', flex: 1.5 },
  { headerName: 'HC', field: 'hc', flex: 0.6 },
  {
    field: 'status',
    flex: 0.8,
    cellRenderer: StatusComponent,
    cellRendererParams: (params) => ({
      status: params.data
    })
  },
  { field: 'date', flex: 1, valueGetter: () => '28/July' },
  {
    field: 'Ch 1',
    flex: 0.8,
    cellRenderer: ButtonComponent,
    cellRendererParams: (params) => ({
      showChallenger: (player) => {
        emit('togglePopUp', player)
      },
      person: params.data,
      row: params.node.rowIndex,
      col: 0
    })
  },
  {
    field: 'Ch 2',
    flex: 0.8,
    cellRenderer: ButtonComponent,
    cellRendererParams: (params) => {
      return {
        showChallenger: (player) => {
          emit('togglePopUp', player)
        },
        person: params.data,
        row: params.node.rowIndex,
        col: 1
      }
    }
  },
  {
    field: 'Ch 3',
    flex: 0.8,
    cellRenderer: ButtonComponent,
    cellRendererParams: (params) => ({
      showChallenger: (player) => {
        emit('togglePopUp', player)
      },
      person: params.data,
      row: params.node.rowIndex,
      col: 2
    })
  },
  {
    field: 'Ch 4',
    flex: 0.8,
    cellRenderer: ButtonComponent,
    cellRendererParams: (params) => ({
      showChallenger: (player) => {
        emit('togglePopUp', player)
      },
      person: params.data,
      row: params.node.rowIndex,
      num: 3
    })
  }
])
</script>

<template>
  <ag-grid-vue
    :rowData="rowData"
    :columnDefs="colDefs"
    style="height: 500px"
    class="ag-theme-quartz"
  >
  </ag-grid-vue>
</template>

<style scoped></style>
