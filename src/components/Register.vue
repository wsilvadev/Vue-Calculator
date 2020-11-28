<template>
    <div id="app">
        <div id="inputs">
            <h3>Nome</h3>
            <input type="text" v-model="name" />
            <h3>Email</h3>
            <input type="email" v-model="email" />
            <h3>Idade</h3>
            <input type="number" v-model="age" />
            <Button id="button" value="Registrar" @clicking="Reg"></Button>
        </div>
    </div>
</template>

<script>
import Button from './Button.vue';
export default {
    name: 'App',
    data() {
        return {
            name: '',
            email: '',
            age: ''
        };
    },
    props: {},

    components: {
        Button
    },
    methods: {
        Reg: function() {
            this.$emit('register', {
                name: this.name,
                email: this.email,
                age: this.age
            });
            this.name = '';
            this.email = '';
            this.age = '';
        }
    }
};
</script>

<style scoped>
#inputs {
    text-align: start;
    margin-top: 1rem;
    margin-left: 2rem;
    width: 390px;
    padding: 2rem;
    background-color: aqua;
    border-radius: 1rem;
}
input {
    width: 20rem;
    font-size: 30px;
}
#button {
    margin-top: 2rem;
}
</style>
