<template>
  <div id="app">
    Y<form action="https://www.google.com">
        <vue-tel-input
        v-model="mobile"
        @validate="check"
        style="width:50%"
        />
        <p style="color:yellowgreen">{{message}}</p><br>
        <input type="submit" value="Submit" v-if="!error">
    </form>
  </div>
</template>
<script>

import {VueTelInput} from 'vue-tel-input';
import 'vue-phone-number-input/dist/vue-phone-number-input.css';

    export default {
        name: "PhoneNo",
        components: {
            VueTelInput
        },
        data: () => ({

            mobile:'',
            error:true,
            message:''
        }),
        methods:{
            check({ isValid}){
                if(isValid===true){
                    this.error=false
                    this.message="Valid Phone Number"
                }
                else{
                  this.error=true
                  this.message=''
                }
            }
        }
    };
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
