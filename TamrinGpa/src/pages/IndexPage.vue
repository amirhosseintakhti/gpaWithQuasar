<template>
  <q-page >
    <div class="row q-gutter-xs flex-center">
      <div class="col-xs-8 col-md-10 q-ma-xs q-pa-xs">
        <q-input
        class="q-gutter-xs q-mt-xs"
      v-model="text"
      label="name"
    />


      </div>
      <div class="col-xs-8 col-md-10 q-ma-xs q-pa-xs">
        <q-input
        class="q-gutter-xs q-mt-xs"
      v-model="text"
      label="grade"

    />
      </div>
      <div class="col-7 marging flex flex-center">
        <q-btn style="background: #FF0080; color: white;width: 100%;" label="avg" />
      </div>
    </div>


  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>
