<template>
    <div id="app">
        <h1>Cadastro De Usuários</h1>
        <div id="container">
            <Register @register="registerUser" />
            <div id="userContainer">
                <div v-for="user in users" v-bind:key="user.id">
                    <Users
                        :id="user.id"
                        :email="user.email"
                        :name="user.name"
                        :age="user.age"
                        @deleteUser="deleteUserId"
                    />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Users from './components/Users.vue';
import Register from './components/Register.vue';

export default {
    watch: {},
    name: 'App',
    data() {
        return {
            users: []
        };
    },

    components: {
        Users,
        Register
    },
    methods: {
        registerUser: function($event) {
            if ($event.name.length < 2 || $event.email < 2 || $event.age < 1) {
                alert('Os campos precisam ser preenchidos');
            } else {
                this.users.push({
                    id: Date.now(),
                    name: $event.name,
                    email: $event.email,
                    age: $event.age
                });
            }
        },
        deleteUserId: function($event) {
            const usersFilter = this.users.filter(
                item => item.id !== $event.id
            );
            return (this.users = usersFilter);
        }
    }
};
</script>

<style scoped>
#container {
    display: grid;
    grid-template-columns: 40rem 60rem;
}
#userContainer {
    margin-top: 3rem;
    display: grid;
    grid-template-columns: 300px 300px 300px;
    grid-gap: 100px;
    color: dimgray;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    height: 10rem;
}

h1 {
    text-align: center;
}
</style>
