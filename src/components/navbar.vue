<template>
  <div class="main">
<nav>
    <div id="contain">
        <router-link :to="'/'" exact>Home</router-link>
        <router-link :to="'/avengers'">Heros</router-link>
    </div> 
</nav>
  </div>
</template>


<!-- css part -->
<style scoped>
nav{
  overflow: hidden;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 5;
  
}
.main{
    text-align: center;
}

a{
    color: white;
}
#contain{
    background: linear-gradient(45deg, #353535cf, #9e9e9e,#696969,#717071,#81878c);
    height: 50px;
    color: white;
    position: fixed top;

}
#contain a{
    text-decoration: none;
    position: relative;
    top:10px;
    font-size: 18px;
    margin: 10px;
    padding: 5px;
}
.router-link-exact-active,.router-link-active:focus{
    background: #efe9e9;
    color: black;
    border-radius: 15px 0px;
    transition: all 0.5s ease;
    padding: 3px;
}
@media only screen and (max-width: 600px){
  #contain{
    background:linear-gradient(45deg, red,blue);
  }
}
</style>

<!-- js part -->

<script>
export default {
}
</script>