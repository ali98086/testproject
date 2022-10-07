<template>

<hr>
  <ul>
    <li><b><u>UserAgent</u></b></li>  
    <br>
    <li>{{userAgent.username}}</li>
    <li>{{userAgent.password}}</li>
  </ul>
<hr>
</template>

<script>
export default {
  inject: ['userAgent'],
};
</script>

<style>
</style>