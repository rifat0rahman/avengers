<template> 
  <div class ="container-fluid" style="position:relative;left:0px;padding:0px;margin:0px;top:50px">
    <div class="row container-fluid">
        <div class="col1"  v-for = 'hero in heros' :key = 'hero'>
         <div class="con" id="bg">
            <img :src="hero.image.url">
            <p>{{hero.name|snippets}}</p>
            <routerLink :to ="'/avengers/'+ hero.key" ><button>More</button></routerLink>
        </div>
        </div>
    </div>
</div>
</template>


<!-- css part -->
<style>

.col1:hover{
    box-shadow: 1px 1px 5px 0px #7b6969;
}
.col1 button:focus{
    outline: none;
    border: 2px solid #eee;
}
.con{
    flex: 20%;
    width: 200px;
    height: 270px;
    border: 4px solid #eee;
    background: linear-gradient(90deg, #2d6998, #9e0303);
    
}
.row{
    display: flex;
    flex-wrap: wrap;
    padding: 0px;
    margin: 0px;
    position: absolute;
    justify-content: space-around;
    
}
.col1{
    text-align: center;
    margin: 10px;
    
}
.col1 img{
    width: 180px;
    padding: 5px;
    height: 180px;

}
.col1 p{
    font-size: 30px;
    font-family: arial;
    color: white;
    text-shadow: 2px 2px black;
    position: relative;
    top:-5px;

}
.col1 button{
    font-family: monospace;
    background: #006ca0;
    color: #f7eeee;
    border-radius: 20px 0px 20px;
    font-size: 18px;
    padding: 4px;
    border:2px solid black;
    margin: 0px;
    position: relative;
    bottom: 25px;


}

*{
    padding: 0px;
    margin: 0px;
}

</style>

<!-- js part -->

<script>
import data from '../api.js'
import axios from 'axios'
export default {
    data(){
       return{
        data:[],
        a:'#'+Math.random().toString().slice(3,9),
        b:'#'+Math.random().toString().slice(2,8),
        att:'',
        heros:[],
        msg:''
        
       }
    },
    created(){
        this.att = 'linear-gradient'+'('+'90deg'+','+this.a+','+this.b+')'; 
        this.data = data;
    },
    mounted(){
        axios.get('https://super-hero-c9cf4.firebaseio.com/posts.json').then(data=>{
            var temp=[];
            for(let key in data.data){
                data.data[key].key = key
                temp.push(data.data[key])

            }
            this.heros = temp
        })


}
        
}


</script>