<template>
    <form @submit.prevent>
            <input 
                v-model="post.title"
                class="input" 
                type="text" 
                placeholder="Название">
            <input 
                v-model="post.body"
                class="input" 
                type="text" 
                placeholder="Описания">
            <button 
                class="btn" 
                @click="createPost()">Создать
            </button>
        </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: '',
                body: '',
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post, 'secons')
            this.post = {
                title: '',
                body: '',
            }
        },
    }
}
</script>

<style scoped>

form {
    display: flex;
    flex-direction: column;

}

.input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
}

.btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background-color: none;
    border: 1px solid teal;
    color: teal;
}


</style>