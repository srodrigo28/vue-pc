<template>
    <div
        @click="$emit('taskStateChanged', task)" 
        class="task" :class="stateClass">
        <span @click.stop="$emit('taskDeleted')" class="close">X</span>
        <p> {{ task.name }} </p>
    </div>
</template>
<script>
    export default{
        props: {
            task: { type: Object, required: true }
        },
        computed: {
            stateClass(){
                return {
                    pending: this.task.pending,
                    done: !this.task.pending
                }
            }
        }
    }
</script>
<style>
    .task{
        position: relative;
        box-sizing: border-box;
        width: 350px;
        height: 150px;
        padding: 10px;
        border-radius: 8px;
        font-size: 2rem;
        font-weight: 300;
        cursor: pointer;
        user-select: none; /** para não permitir que selecione o html ou texto */
        display: flex;
        justify-content: center;
        align-content: center;
    }
    .pending{
        border-left: 30px solid #B73229;
        background-color: #F44336;
    }
    .done{
        color: #DDD;
        border-left: 30px solid #0A8F08; /** efeito bordar a esquerda */
        border-right: 30px solid #0A8F08; /** efeito bordar a esquerda */
        background-color: #4CAF50;
        text-decoration: line-through; /** fazer o efeito risco */
    }
    .pending .close{ background-color: #B73229; }
    .done .close{ background-color: #0A8F08; }
    .close { 
        position: absolute; right: 10px; top: 10px;
        font-size: 0.9rem; font-weight: 600; height: 20px; 
        width: 20px; border-radius: 10px; display: flex; justify-content: center;
    }
</style>

