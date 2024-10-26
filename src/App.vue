<script setup>
  import {onMounted, ref} from 'vue'
  import PocketBase from 'pocketbase'

  const titleval=ref("")
  const data=ref([])
  

  const db = new PocketBase("http://127.0.0.1:8090")

  const titleVal=ref("")

  async function submit(){
    const data={
        title: titleVal.value,
        description : "desc",
    }
    await db.collection("posts").create(data)
    data.value.push(record)
  }

  onMounted(async()=>){
    const value = await db.collection("posts").getFullList();
    data.value= result;
  }




</script>



<template>
 <input v-model="titleVal"/>
 <button @click="submit">Add</button>
</template>