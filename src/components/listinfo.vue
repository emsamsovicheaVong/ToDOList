<template>

    <div class="">
        <div class="info">            
            <input type="text" placeholder="Enter the Task" class="inputtype" v-model="taskInput" @keyup.enter="pushToArray">        
        </div>
        <div class="container1">
        <div class="infoToDo" v-for="(arrayinf,index) in arrayinfo" :key="arrayinf.id">
            <div>
                 <button @click="removeArr(index)" class="buttonX">X</button>
                <p class="card" v-if="{completed}">{{arrayinf.task}}</p>
                <input type="checkbox" @click="plusItem" class="checkBox" :class="{completed:arrayinf.completed}" v-model="arrayinf.completed">

                <div>      
            </div>
            </div>
        </div>
         <div class="extra">
                <label class="checkAll"><input type="checkbox" :checked="!checkReactive" @change="checkAllToDo"> Check All </label>
                <div>{{itemLeft}} Item Completed</div>    
            </div>  
        </div>
    </div>

</template>
<script>
export default {
    data(){
        return{
            taskInput:"",
            xbutton:true,
            idToList:0,
            arrayinfo:[]
        }
    },
    computed:{
        itemLeft(){
            return this.arrayinfo.filter(arrayinf=>arrayinf.completed).length
        },
        checkReactive(){
            return this.itemLeft !=this.arrayinfo.length
        }

    },
    methods:{
        pushToArray:function(){
            if(this.taskInput.trim()==0){
                return
            }
            this.arrayinfo.push({
                id:this.idToList,
                task:this.taskInput,
                completed:false

            })
            this.taskInput="",
            this.idToList++,

            alert('You have add the new')
        },
        removeArr:function(index){
            this.arrayinfo.splice(index,1)
        },
        plusItem:function(){
            this.itemLeft++;
        },
        checkAllToDo(){
            this.arrayinfo.forEach((arrayinf)=> arrayinf.completed = event.target.checked)
        }
        
    }
}
</script>
<style scoped>
.checkBox{
    margin-left: 600px;
}
.info{
    height: 100px;
    border-color: blueviolet;
}
.infoToDo{
    margin-top: 10px;
    justify-content: space-between;

 
}
.inputtype{
    width: 70%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;
}
.psize{
   font-size: 20px;
  text-align: left;
  margin-top: 30px;
  margin-left:50px ; 
}

.buttonX{
    border-radius: 30%;
    border: none;
    padding: 10px;
    margin: 1px 1px;
    cursor: pointer;
    background-color: burlywood;
    margin-left: 600px;
    transition-duration: 0.10s;            
    justify-content: space-between;
    position: absolute;
    right: 0;
    


}
.buttonX:hover{
    color: black;
    background-color: cadetblue;
}
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 80%;
  height: 35px;
  align-content: center;
  margin-left:50px ;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}
.complete{
  background-color: red;
}
.checkAll{
    margin-right: 500px;
}
.extra{
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size:16px ;
    border-top: 1px solid lightgrey;
    padding-top: 16px;
    margin-bottom: 16px;
}

</style>