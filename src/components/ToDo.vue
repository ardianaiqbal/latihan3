<template>
  <div>
    <ol>
      <li v-bind:key="daftar" v-for="daftar in listDaftar">
        {{ daftar }}
      </li>
    </ol>
  </div>

  <input v-model="tambahList" v-on:keyup.enter="tambahkan"/>
  <button @click="tambahkan">tambahkan</button>
  <p v-if="jumlah >= 4">Hebat!</p>
  <div></div>
</template>
  
  <script>
export default {
  name: "ToDo",
  data() {
    return {
      listDaftar: [],
      jumlah: 0,
    };
  },
  methods: {
    tambahkan() {
        if(this.tambahList!=null&&this.tambahList!=''){
            this.listDaftar.push(this.tambahList);
      this.jumlah++;
      this.tambahList = "";
        }
        else{
            null;
        }
      
    },
  },
};
</script>

<style scoped>
</style>
  