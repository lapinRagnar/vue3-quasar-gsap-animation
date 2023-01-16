<template>
  <q-page padding>

    <h3 class="text-center">Ma Calculatrice</h3>

    <div class="row justify-center">

      <div class="row bg-grey rounded-borders q-gutter-xs q-pa-lg" style="width: 60%;">

        <div class="q-mx-md q-pa-md text-right bg-amber rounded-borders" style="width: 100%;">
          {{ previous_value || '.' }}
        </div>

        <div class="q-mx-md q-pa-md text-right bg-cyan-10 text-h4 rounded-borders" style="width: 100%;">
          {{ current_value || '0' }}
        </div>


        <q-btn-group style="width: 100%;" class="q-gutter-xs">
          <q-btn
            size="22px"
            flat
            unelevated
            v-for="item in operator_line1"
            class="col bg-blue-grey-8 text-white"
            :label="item"
            @click="calculator(item)"
          />
        </q-btn-group>

        <q-btn-group style="width: 100%;" class="q-gutter-xs">
          <q-btn
            size="22px"
            flat
            unelevated
            v-for="item in operator_line2"
            class="col bg-blue-grey-8 text-white"
            :label="item"
            @click="calculator(item)"
          />
        </q-btn-group>

        <q-btn-group style="width: 100%;" class="q-gutter-xs">
          <q-btn
            size="22px"
            flat
            unelevated
            v-for="item in operator_line3"
            class="col bg-blue-grey-8 text-white"
            :label="item"
            @click="calculator(item)"
          />
        </q-btn-group>

        <q-btn-group style="width: 100%;" class="q-gutter-xs">
          <q-btn
            size="22px"
            flat
            unelevated
            v-for="item in operator_line4"
            class="col bg-blue-grey-8 text-white"
            :label="item"
            @click="calculator(item)"
          />
        </q-btn-group>

        <q-btn-group style="width: 60%;" class="q-gutter-xs">
          <q-btn
            size="22px"
            flat
            unelevated
            v-for="item in operator_line5"
            class="col bg-blue-grey-8 text-white"
            :label="item"
            @click="calculator(item)"
          />
        </q-btn-group>

      </div>


    </div>



  </q-page>
</template>

<script setup>

  import { ref } from 'vue';

  const previous_value = ref('')
  const current_value = ref('')
  const operator_line1 = ['C', '+', '-', '*']
  const operator_line2 = [7, 8, 9, '/']
  const operator_line3 = [4, 5, 6, '%']
  const operator_line4 = [1, 2, 3, '=']
  const operator_line5 = [0, '.']
  const operator = ref('')

  function calculator(item){

    console.log('marche', item)
    console.log('marche', isNaN(item))
    if (!isNaN(item) || item == '.') {
      current_value.value += item
    }

    if (item == 'C') {
      current_value.value = ''
      previous_value.value = ''
    }

    if (['+', '-', '*', '/', '%'].includes(item)) {
      operator.value = item
      previous_value.value = current_value.value + ' ' + item
      current_value.value = ''
    }

    if (item == '=') {
      previous_value.value += current_value.value
      current_value.value = eval(previous_value.value)
    }
  }

</script>
