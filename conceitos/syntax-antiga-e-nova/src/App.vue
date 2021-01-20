<template>
  <div>
    <h1>Minha Lista de tarefas!</h1>
    <button @click="handleShowHideList()">
        Ver a Lista!
    </button>
    <br>
    <input type="text" @keyup.enter="addTask" v-focus v-model="state.currentTask">
    <ul v-if='state.showList'>
        <li v-for="(task, index) in state.tasks" @dblclick="complete(task)" class="task-item" :class="{'line-through': task.isDone}" :key="`${task}-${index}`">
            {{task.name}}
            <button @click="remove(task)">&times;</button>
        </li>
    </ul>
    <p v-else>Lista de tarefas escondidas</p>
  </div>
</template>

<script>
import {reactive} from 'vue'
const focus = {
    inserted: (el) => {
        el.focus()
    }
}


export default{
    directives:{
        focus
    },
    setup(){
        const state = reactive({
            currentTask:'',
            showList: false,
            tasks: [
                {name: 'Fazer curso', isDone: false}
            ]
        })

        function handleShowHideList(){
            state.showList = !state.showList
        }

        function remove(task){
            state.tasks = state.tasks.filter(t => {
                t.name !== task.name
            })
            console.log(task)

        }

        function complete(task){
            state.tasks = state.tasks.map(t => {
                if(t.name === task.name){
                    return({...t, isDone: !t.isDone})
                }
                return{...t}
            })
        }

        function addTask(){
            state.tasks.push({
                name: state.currentTask,
                isDone: false
            })
            state.currentTask = ''
        }
        return {
            state,
            handleShowHideList,
            complete,
            remove,
            addTask
        
        }
    }
}

</script>

<style>
.line-through{
    text-decoration: line-through;
}
.task-item{
    cursor: pointer;
}
</style>