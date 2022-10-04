<template>
  <hr />
  <h2>Form Comment</h2>
  <form>
    <label for="comment">نظر</label>
    <input id="comment" type="text" v-model="comment" />
    <!-- <button id="commentbtn" @click.prevent="sendComment($event , sendcomment)">درج نظر</button> -->
  </form>

  <div>
    <p>نظر وارد شده</p>
    <p class="p2" v-text="comment"></p>
    <!-- Or <p class="p2">{{comment}}</p> -->
  </div>

  <hr />
</template>

<script>
export default {
    
  data(){
    return{

      comment: ''


  }}


};
</script>

<style>
</style>