<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" siteName="webSiteName" />

  <h1 v-if="fname === 'reza'">{{ fname }}</h1>
  <h1 v-else>Name is nt ali</h1>

  <p v-text="checknumber()"></p>

  <ul style="list-style-type: none; padding: 0">
    Colors
    <li v-for="(color, index) in colors" :key="index">{{ color + "" }}</li>
  </ul>

  <table :style="tablestyle">
    <tr>
      <th>Colors</th>
    </tr>

    <tr v-for="(color, index) in colors" :key="index">
      <td>{{ color }}</td>
    </tr>
  </table>

  <CommentForm />
 

  <div>
    <p>برای دریافت نام وبسایت روی دکمه کلیک کنید</p>
    <button @click="webSiteName($event, 'janbo shopping')">دریافت نام</button>
    <p>{{ websitename }}</p>
  </div>

  <input :class="{red: redbgcolor}" ref="input" type="text" placeholder="روی کادر دابل کلیک کنید" @dblclick="changeBgColor()"/>

<UserInf :user-info = 'userInfo' @showinf="setStatus($event)"/>
   <span>
    : وضعیت دریافت لیست کاربر
  <p>{{statusInfList}}</p>
  </span>

</template>




<script>
import HelloWorld from "./components/HelloWorld.vue";
import CommentForm from "./components/CommentForm.vue";
import UserInf from "./components/UserInf.vue";

export default {
  name: "App",

  data() {
    return {
      fname: "ali",
      grade: 10,
      websitename: "",
      redbgcolor: false,

      tablestyle: {
        margin: "0 auto",
        border: "2px solid blue",
      },

      checknumber: () => {
        return this.grade > 15 ? "Good" : "normal";
      },

      colors: ["red", "blue", "green"],

      userInfo : {

        fname: 'ali',
        lname: 'hashemi',
        age: 35

      },
      statusInfList: 'عدم نمایش اطلاعات',
        setStatus(sts){

      this.statusInfList= sts;

    }


    }
  },

  methods: {
    webSiteName(event, name) {
      setTimeout(() => {
        this.websitename = name;
        console.log(event.target);
      }, 2000);
    },

    changeBgColor(){

      this.redbgcolor= true;
      this.$refs.input.style.height= '30px';

    },



  },

  components: {
    HelloWorld,
    CommentForm,
    UserInf
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

tr,
td,
th {
  border: 2px solid blue;
}
form {
  margin-top: 30px;
  margin-bottom: 30px;
}

.p2 {
  border: 2px groove black;
}

form,
.p2 {
  direction: rtl;
}

button {
  min-width: 70px;
  min-height: 30px;
}

.red{

  background-color: red;

}

#commentbtn{

  margin-right: 10px;

}
ul{

  padding: 0;
  list-style-type: none;
}


</style>
