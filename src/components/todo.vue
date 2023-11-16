<script>
export default{
    data(){
        return{
            listData:['makan','tidur'],
            todoContent:''
        }
    },
    methods:{
        silang:function(index){
            this.listData.splice(index,1)
        },
        addTodo:function(){
            this.listData.push(this.todoContent)
        }
    }
}
</script>

<template>
<div class="container">
    <h1 class="judul">todolist</h1>
    <div class="todo">
        <div class="col">
            <input type="text" placeholder="whats your todo?" v-model="todoContent">
            <button @click="addTodo">add</button>
        </div>
        <div class="output">
            <h5 v-for="(data,index) in listData" :key="index">{{data}} 
                <i id="ceklis" class="fa-solid fa-check"></i> 
                <i id="silang" @click="silang(index)" class="fa-solid fa-x"></i></h5>
        </div>
    </div>
</div>
</template>

<style scoped>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.container{
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    gap: 20px;
    justify-content: center;
    align-items: center;
}
.judul{
    font-size: 2.5em;
    font-weight: 800;
    text-transform:capitalize;
}
.todo{
    width:100%;
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.col{
    width:100%;
    display: flex;   
    justify-content: center;
    align-items: center;
}
.col:nth-child(1){
    display: flex;
    gap: 10px;
}
.col button{
    padding: 6px 8px;
    border-radius: 5px;
    border: none;
    background-color: orange;
    color: white;
    font-size: 1.1em;
    font-weight: 800;
    text-transform: capitalize;
}
.col input{
    display: inline-block;
    width: 60%;
    border: 1px solid black;
    padding: 10px 20px;
    cursor: pointer;
}
.output{
    margin-top: 5%;
    display: flex;
    width: 100%;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 25px;
}
.output h5{
    width: 100%;
    font-size: 1.5em;
    font-weight: 700;
    text-transform: capitalize;
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.output h5 i{
    font-size: 1.1em;
    cursor: pointer;
}
#silang{
    color: red;
}
#ceklis{
    color: greenyellow;
}
</style>