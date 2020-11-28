<template>
    <div id="container">
        <p>nome: {{ name }}</p>
        <br />
        <p>Email: {{ email }}</p>
        <br />
        <p>Idade: {{ age }}</p>
        <br />
        <button @click="deleteUser">Deletar</button>
    </div>
</template>

<script>
export default {
    data() {
        return {};
    },
    props: {
        id: Number,
        name: String,
        email: String,
        age: String
    },
    methods: {
        deleteUser: function() {
            this.$emit('deleteUser', { id: this.id });
        }
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#container {
    background-color: antiquewhite;
    padding: 30px;
    width: 20rem;
}
button {
    width: 100px;
    text-align: center;
    margin-left: 100px;
}
</style>
