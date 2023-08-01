<template>
  <div class="q-ml_sm">
    <q-table
      :title="title"
      :rows="rows"
      :columns="columns"
      row-key="name"
    />
  </div>
</template>
<script>
import {defineComponent} from 'vue'


export default defineComponent({
  name: "BaseTable",

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
