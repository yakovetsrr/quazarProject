<template>
  <q-page>
   <ToolbarCellFilter/>
   <BaseTable :columns="columns" :rows="rows" :title="title"/>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import ToolbarCellFilter from "components/ToolbarCellFilter.vue";
import BaseTable from "components/ui/BaseTable.vue";

const columns = [
  { name: 'depot_no', align: 'center', label: 'Склад', field: 'depot_no', sortable: true },
  { name: 'cell_no', label: 'Ячейка', field: 'cell_no', sortable: true },
  { name: 'max_weight', label: 'Максимальный вес', field: 'max_weight' },
  { name: 'max_uld', label: 'Максимальное кол-во СП', field: 'max_uld' },
  {name: 'section', label: 'Секция', field: 'section', sortable: true },
  { name: 'remtext', label: 'Примечание', field: 'remtext' }]
const  rows = [
  {
    depot_no: 'WIS',
    cell_no: 'ULD01',
    max_weight: '',
    max_uld: '',
    section: 'ULD',
    remtext: '',
  }]
export default defineComponent({
  name: 'IndexPage',
  components: {BaseTable, ToolbarCellFilter},

  data(){
    return{
      columns: columns,
      rows: rows,
      title: 'Справочник',
    }
  }
})
</script>
