<script setup>
    const props = defineProps(['tarefas'])
</script>


<template>
    <ul class="list-group mt-4" >
        <li v-if="props.tarefas.length === 0" class="list-group-item">
            Não há tarefas pendentes.
        </li>
        <li v-else class="list-group-item" v-for="tarefas in props.tarefas/*getTarefasFiltradas()*/">
            <input @change="evento => tarefas.finalizada = evento.target.checked" type="checkbox" :checked="tarefas.finalizada" :id="tarefas.titulo">
            <label :class="{ done: tarefas.finalizada}" class="ms-3" :for="tarefas.titulo">
            {{ tarefas.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
