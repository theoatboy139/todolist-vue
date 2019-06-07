<template>
    <div>
        <h1 font: Arial>Todo Table List</h1>
        <ul>
            <li v-for="(task,index) in tasks" :key="index">
                {{index+1}} : {{task}}
                <button type = "button" width:auto height:auto @click="removeTask(index)">Remove</button>
                <!-- <button type = "button" width:auto height:auto @click="setTaskDone(index)">Done</button> -->
            </li>
        </ul>
        <input type="text" width="20" height="5" v-model="newTask" @keyup.enter="addTask()">
        <button type="button" width = "20" height = "5" @click="addTask()">Add task</button>
    </div>
</template>


<script>
import Vue from 'vue'
import Vuex from 'vuex'

export default {
    data() {
        return {
            newTask : "",
            tasks : ["task1"]
        }
    },
    methods:{
        addTask : function() {
            this.tasks = [...this.tasks,this.newTask]
            //this.tasks.push(this.newTask)
            this.newTask = ""
        },

        removeTask : function(index) {
            this.tasks = this.tasks.filter((v,i)=>{
                return i != index
            })
            //this.tasks.splice(index,1) working = OK
        },

        setTaskDone : (index) => {

        }
    }
}
</script>

<style>

</style>


