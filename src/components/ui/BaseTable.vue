<template>
  <div class="q-ml_sm">
    <q-table
      :title="title"
      :rows="rows"
      :columns="columns"
      row-key="name"
    >
      <template #body-cell-actions>
        <q-td>
          <BaseButton icon="edit" flat color="primary"></BaseButton>
          <BaseButton icon="delete" flat color="red"></BaseButton>
        </q-td>
      </template>
    </q-table>
  </div>
</template>
<script>
import {defineComponent} from 'vue'
import BaseButton from "components/ui/BaseButton.vue";


export default defineComponent({
  name: "BaseTable",
  components: {BaseButton},

  props: {
    columns: {
        type: Array,
        required: true,
        default: () => [],
    },
    rows: {
      type: Array,
      required: true,
      default: () => [],
    },
    title: {
      type: String,
    }
  }

})
</script>
<style scoped lang="scss">

</style>
