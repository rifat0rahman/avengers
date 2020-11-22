<template>
  <div style="position:relative;top:40px;" class="bg">
    <h1 class="h1" style="font-family:monospace;text-align:center;margin-top:10px">Hey dear!!know about me..</h1>
    <div style="padding:15px 15px;margin:auto" class="bg">
        <div class="row bg">
            <div class="col1">
                <img :src="heros.image.url">
            </div>
            <div class="col2">
                <p>Name</p>
                <li>{{heros.name}}</li>
                <div>
                   <ul>Aliases
                    <li>{{heros.biography.aliases[0]}}</li>
                    <li>{{heros.biography.aliases[1]}}</li> 
                   </ul>
                </div>
                <p>Rule</p>
                <li>{{heros.biography.alignment}}</li>
                <p>Full-name</p>
                <li>{{heros.biography.full-name}}</li>
                <p>Activity</p>
                <li>{{heros.connections.group-affiliation}}</li>
                <p>Relatives</p>
                <li>{{heros.connections.relatives}}</li>
                <p>Occupation</p>
                <li>{{heros.work.occupation}}</li>

            </div>
        </div>
    </div>
  </div>
</template>

<!-- cdss -->
<style scoped>
*{
    padding: 0px;
    margin: 0px;
    font-family: monospace;
}
.row{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    padding: 15px 15px;
    margin: auto;
}
.col1{
    flex:40%;
    max-width: 400px;
    height: 430px;
    position: relative;
    margin: 10px;
    border: 5px solid #eee
}
.col1 img{
    width: 100%;
    height: 100%;
}
.col2{
    flex: 40%;
    background: #b6bbb11f;
    font-size: 18px;
    padding: 10px;
    margin: 10px;
    border-left: 1px solid #e2e0e0;
    float: right;
}
.col2 li{
    position: relative;
    left: 30px;
}
.col2:hover{
    box-shadow: 0px -3px 4px 0px #865bd496;
}
@media only screen and (max-width: 600px){
    .col1{
        flex: 100%;
    }
    .col2{
        flex: 100%;
    }
    .h1{
        font-size: 30px;
        top: 20px;
        position: relative;
    }
}





</style>


<script>
import axios from 'axios'
export default {
 data(){
    return {
        id:this.$route.params.id,
        heros:[]
    }
 },
 mounted(){
    axios.get('https://super-hero-c9cf4.firebaseio.com/posts/'+this.id+'.json').then(data=>{
        this.heros = data.data
    })
 }
}
</script>