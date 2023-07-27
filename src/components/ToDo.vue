<template>
  <div>
    <ol>
      <li v-bind:key="daftar" v-for="daftar in listDaftar">
        {{ daftar }}
      </li>
    </ol>
  </div>

  <input v-model="tambahList" @keyup.enter="tambahkan"/>
  <button @click="tambahkan">Tambahkan</button>
  <p v-if="minimalEmpat">Hebat!</p>
  <div></div>
</template>
  
  <script>
export default {
  name: "ToDo",
  data() {
    return {
      listDaftar: [],
    };
  },
  methods: {
    tambahkan() {
        if(this.tambahList.trim()!=null&&this.tambahList.trim()!=''){
            this.listDaftar.push(this.tambahList);
      this.tambahList = "";
        }
        else{
            null;
        }
      
    },
  },
  computed:{
    minimalEmpat(){
      return this.listDaftar.length>=4
    },
  },
};
</script>

<style scoped>
</style>
  