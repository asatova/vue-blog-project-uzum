<template>
<div class="wrapper">
  <div class="container">
    <h1>Welcome to My Vue App</h1>
    <p>This is a simple Vue.js application.</p>
    <input type="text" placeholder="Type city..." />
    <button >Get</button>
  </div>
 </div>
</template>

<style scoped>
.wrapper {
width: 900px;
height: 500px;
border-radius: 50px;
background-color: bisque;
padding: 20px;
}

.wrapper h1 {
  color: darkblue;
  margin-top: 50px;
}
.wrapper input {
  margin-top: 30px;
  background: transparent;
  border: 0;
  border-bottom: 2px solid darkblue;
  padding: 10px;
}
.wrapper input:focus {
  outline: none;
  border-bottom: 2px solid darkred;
  
}
.wrapper button {
  margin-top: 30px;
  background-color: darkblue;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  margin: 20px;
}
</style>
<script>


</script>