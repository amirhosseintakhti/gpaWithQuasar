<template>
  <q-page >
    <div class="row q-gutter-xs flex-center">
      <div class="col-xs-8 col-md-10 q-ma-xs q-pa-xs">
        <q-input
        class="q-gutter-xs q-mt-xs"
      v-model="name"
      label="name"
    />


      </div>
      <div class="col-xs-8 col-md-10 q-ma-xs q-pa-xs">
        <q-input
        type="number"
        class="q-gutter-xs q-mt-xs"
      v-model="grade"
      label="grade"

    />
      </div>
      <div class="col-7 marging flex flex-center" v-for="student in list" :key="student">
        <h2>{{student.name}}</h2>
        <h2>{{student.grade}}</h2>
      </div>
      <div class="col-7 marging flex flex-center">
        <q-btn @click="add()" style="background: #FF0080; color: white;width: 100%;" label="add+" />
      </div>
      <div class="col-7 marging flex flex-center">
        <q-btn @click="avg()" style="background: #FF0080; color: white;width: 100%;" label="avg" />
      </div>
      <div class="col-7 margin flex flex-center">
        <h2>{{  }}</h2>
      </div>
    </div>


  </q-page>
</template>

<script>
import { defineComponent, reactive,toRefs } from "vue";

export default defineComponent({
  name: "IndexPage",
  setup(){
    const props = reactive({
      total:0,
      av:null,
      name:'',
      grade:null,
      list:[],
    });
    function add(){
      props.list.push({
        name:props.name,
        grade:props.grade
      });
      props.name='';
      props.grade=null;
    }
    function avg(){
      props.list.forEach((val)=>{
        props.total+=parseFloat(val.grade)
      });
      props.av = props.total/props.list.length;
      console.log(props.av)
    }
    return{
      ...toRefs(props),
      add,
      avg
    }
  }
});
</script>
