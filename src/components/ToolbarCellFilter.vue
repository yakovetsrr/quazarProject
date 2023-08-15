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
     <BaseButton @click="()=>isDialogVisible=!isDialogVisible" label="Добавить"/>

      <q-dialog v-model="isDialogVisible" persistent>
        <q-card>
          <q-card-section class="row items-center q-pb-none">
            <div class="text-h6">Добавление ячейки склада</div>
            <q-space />
            <q-btn icon="close" color="blue" flat round dense v-close-popup />
          </q-card-section>

          <q-card-section>
            <q-form class="q-pa-md">
            <BaseInput v-model="model3" placeholder="Введите ячейку.."></BaseInput>
            <BaseInput v-model="model4" placeholder="Введите ячейку.."></BaseInput>
            </q-form>
          </q-card-section>
          <q-card-section>
            <BaseButton label="Отменить" color="red" v-close-popup/>
            <BaseButton label="Сохранить"/>
          </q-card-section>
        </q-card>
      </q-dialog>
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
      isDialogVisible: false,
      model3:  '',
      model4:'',
    }
  }
})
</script>

<style lang="scss" scoped>
.select {
  width: 250px;
}
</style>

