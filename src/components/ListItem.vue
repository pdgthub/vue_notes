<template>
<div class="list-item">
  <h4>{{note.title}} </h4>
  <p>{{note.text}}</p>
</div>
</template>

<script>
export default {
    name: "ListItem",
    props: ["note"],
}
</script>

<style scoped>
.list-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
    width: 20%
  }

</style>