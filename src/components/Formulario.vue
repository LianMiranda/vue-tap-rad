<script setup>
    import {ref} from 'vue';
    const emit = defineEmits(['salver-pessoa'])

    const nome = ref('')
    const cpf = ref('')
    const categoria = ref('')

    const onSubmit = () => {
        emit('salvar-pessoa', nome.value, cpf.value, categoria.value)
    }

</script>

<template>
    <form @submit.prevent="onSubmit">
        <div>
            <label for="nome">Nome:</label>
            <input v-model="nome" type="text" id="nome">
            <br>
            <label for="cpf">CPF:</label>
            <input v-model="cpf" type="text" id="cpf">
            <br>
            <label for="categoria">Categoria:</label>
            <input v-model="categoria" type="text" id="categoria">
        </div>

        <button>Salvar</button>
    </form>
</template>