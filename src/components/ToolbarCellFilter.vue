<template>
  <div class="flex justify-between q-pa-md">
    <div class="flex q-gutter-md">
      <BaseSelect class="select" v-model="model" :options="options" />
      <BaseSelect class="select" v-model="model2" :options="options2" />
    </div>
    <div class="flex q-gutter-x-md">
      <BaseInput v-model="search" placeholder="Поиск ячейки..">
        <template #append>
          <q-icon name="search"></q-icon>
        </template>
      </BaseInput>
     <BaseButton/>
    </div>
  </div>

</template>

<script>
import {defineComponent} from 'vue'
import BaseSelect from "components/ui/BaseSelect.vue";
import BaseButton from "components/ui/BaseButton.vue";
import BaseInput from "components/ui/BaseInput.vue";

export default defineComponent({
  name: "ToolbarCellFilter",
  components: {BaseInput, BaseButton, BaseSelect},

  data(){
    return{
      model: '',
      model2: '',
      search: '',
      options: ['1', '2', '3'],
      options2: ['1', '2', '3'],
    }
  }
})
</script>

<style lang="scss" scoped>
.select {
  width: 250px;
}
</style>

