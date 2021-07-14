<template>
  <div>
    <NavBar />
    <div class="container mt-2">
      <h1 class="text-primary">Welcome to the page</h1>
      <h3 v-if="$auth.loggedIn">
      {{$auth.user.name}}
      </h3>
    </div> 
  </div>
</template>

<script>
export default {
  auth: false
}
</script>

<style>
body{
  background-color: beige;
}
</style>