<template>
    <div id="custom-overlay-wrapper" v-if="canShow">

        <div id="custom-overlay" @click="hideMe"></div>
             
             <div id="custom-select">
                 <span>{{title}}</span>
                  
                  <ul>
                      <li v-for="(datax,index) in data " :key="index">{{datax}}</li>
                  </ul>
             </div>
            </div>
</template>

<script>
export default {
  props:{
      canShow:{
          default:true
      },
      title:{
          default:"Select"
      },
      selectedIndex:{
          default:-1
      },
      data:{
          default:[]
      }
  },
  mounted(){
    
  },
  methods:{
      hideMe(){
  var overlay = document.getElementById("custom-overlay");
      overlay.addEventListener("click",()=>{
          this.$emit('close');
      })
      }
  }
}
</script>

<style scoped>

#custom-overlay-wrapper{
  position: fixed;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0,0,0,0.4);
  top: 0px;
  left: 0px;
  z-index: 97;


 position: relative;
}

#custom-overlay{
    width: 100vw;
    height: 100vh;
    background-color: red;
    z-index: 99;
    position: absolute;
    top: 0px;
    left: 0px;
}

#custom-select{
  height: 400px;
  width: 400px;
  border-radius: 30px;
  background-color: #0d1117;
   position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 99;
}


</style>