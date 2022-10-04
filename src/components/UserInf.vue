<template>
<hr>
  <ul> لیست اطلاعات کاربر
    <li>{{userInfo.fname}}</li>
    <li>{{userInfo.lname}}</li>
    <li>{{userInfo.age}}</li>
  </ul>
  <hr>
</template>

<script>
export default {

  data(){
    
    return{

      status: 'نمایش لیست اطلاعات کاربر'


  }},



  props:{

    userInfo: Object

  },



    created() {
      
    this.$emit('showinf',this.status);

}
}
</script>

<style>
</style>