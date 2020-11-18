<template>
  <div class="header">
      <img src="../assets/logo.png" class="logo">
      <h1>{{headerName}}</h1>
    </div>
</template>

<script>
export default {
  name: "header",
  data() {
    return {
    headerName: 'Todo App'
    }
  }
}
</script>

<style>
  .header {
    display: flex;
    flex-direction: row;
    align-items: center;
    text-align: center;
  }
  .logo {
    display: block;
    margin: 20px 40px;
    height: 75px;
  }
  h1 {
    text-align: left;
    font-family: Georgia, 'Times New Roman', Times, serif;
  }
</style>