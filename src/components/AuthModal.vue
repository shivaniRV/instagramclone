<script  setup>
import { ref,defineProps } from 'vue';
const open = ref(false);

const props= defineProps((['isLogin']))
const showModal = () => {
  open.value = true;
};

const handleOk = (e) => {
 
  open.value = false;
};
const title= props.isLogin ?'Login' :'Signup'

</script>


<template>
  <div>
    <a-button type="primary" @click="showModal" class="btn">{{ title}}</a-button>
    <a-modal v-model:visible="open" title="title" @ok="handleOk">
      <a-input  class="input" v-if="!isLogin" v-model:value="value" placeholder="Username" />
      <a-input class="input" v-model:value="value" placeholder="Email" />
      <a-input  class="input" v-model:value="value" placeholder="Password" />

      <!-- <p>Some contents...</p>
      <p>Some contents...</p>
      <p>Some contents...</p> -->
    </a-modal>
  </div>
</template>

<style scoped>
 .btn {
margin-left:10px;

 }
 .input{
  margin-top:5px;
 }
</style>
