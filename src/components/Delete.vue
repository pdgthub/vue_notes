<template>
  <button @click="$emit('del-note', note.id)" class="del">x</button>
</template>

<script>

export default {
name: "Delete",
components: {

},
props: ["note"]
}
</script>

<style>
.del 
    {

    
    color: #fff;
    background: #333;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
   
  
}
  
</style>