<template>
  <div class="containerr">
    <div class="text">
        <div class="content">
            <p class="head" id ='time'>ALL SUPER HEROS ARE WAITING FOR YOU!</p>
            <div class="anim">
                <p>
                YOU COULD NOT LIVE WITH YOUR OWN FAILURE, AND WHERE DID THAT BRING YOU? -Thanos
                </p>
                <router-link :to="'./avengers'"><button id="btn">Meet HEROS</button></router-link>
            </div>
        </div>
        
    </div>
    <div>
        
    </div>
  </div>
</template>


<!-- css part -->
<style scoped>
button:focus{
    outline: none;
    background-color: white;
}
button{
    padding: 10px;
    margin: 10px;
    background: #ffe9e9;
    color: black;
    border: 2px solid white;
    font-size: 17px;
    font-family: sans-serif;
    border-radius: 15px;
    box-shadow:0px -3px 6px #08f5d4;
    position: relative;
    top: 25px;

}
.anim a{
    position: relative;
    top: 60px;

}
.anim{
    position: relative;
    top: 150px;
}
.anim p{
    font-size: 20px;
    font-family: monospace;
    color: white;
    animation: anim 15s;
    white-space: nowrap;
    overflow: hidden;

}

@keyframes anim{
    0%{
        width: 0ch;
        position: relative;
    }

    100%{
        width: 79ch;
        position: relative; 
        transition: all 2s ease;
    }
}
.head{
    font-size: 40px;
    color: #235f5c;;
    font-family: monospace;
    position: relative;
    top: 30px;
    text-shadow: 0px -3px 6px #08f5d4, 2px -5px 20px #0fffe8, 1px 2px 2px #fdffff, 0px -1px 0px #f5f5f5;
    animation: all 2s ease


}
.content{
    background:rgb(0,0,0,0.3);
    height: 100%;
    transition: font-size 20px;
}
*{
    margin: 0px;
    padding: 0px;
}
.containerr{
    height:92vh;
    position: relative;
    top: 50px;
}
.text{
    bottom: 0px;
    position: relative;
    text-align: center;
    background-image: url("../img/avergers.jpg");
    height: 100%;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;

}
@media only screen and (max-width: 600px){
    .anim p{
        font-size: 10px;
    }
    .head{
        font-size: 30px;
        top: 40px
    }

}

</style>

<!-- js part -->

<script>


export default {
    data(){
        return{
          shadow:''
        }
    },
    created(){
            setInterval(function() {
                document.getElementById('time').style.textShadow='';
                document.getElementById('btn').style.boxShadow='';
                document.getElementById('time').style.color = 'white';
            },2000)
        },
    mounted(){
          setInterval(function () {
        document.getElementById('time').style.textShadow='0px -3px 6px #08f5d4, 2px -5px 20px #0fffe8, 1px 2px 2px #fdffff, 0px -1px 0px #f5f5f5';
                document.getElementById('btn').style.boxShadow='1px -2px 20px 13px #fb2e00';
                document.getElementById('time').style.color = ' #235f5c';
                document.getElementById('time').style.transition = 'all 2s';
                },3000);
          setInterval(function () {
              document.getElementById('btn').style.transition = '2s';
          },2000)

}
}
</script>