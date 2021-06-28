<template>
<section>
    <header><h1>Users</h1>
    </header>
    <userr-data 
    @add-user="addUser"> 
    </userr-data>
    <active-user
    v-for="user in users"
    :key="user.id"
    :name="user.name"
    :age="user.age"
    > 
    </active-user>
    </section>

</template>

<script>
import ActiveUser from './components/ActiveUser.vue';
import UserrData from './components/UserrData.vue';

export default {
    components: {UserrData, ActiveUser},
    data() {
        return {
            users: [
                {
                    id: 'user1',
                    name: 'Alex',
                    age: '23'
                },
                {
                    id: 'user2',
                    name: 'Sam',
                    age: '20'
                },
            ],

        };
    },
    methods: {
        addUser(name, age) {
            const newUser = {
                id: new Date().toISOString(),
                name: name,
                age: +age
            };
            this.users.push(newUser);
        },
    },
};

</script>
<style>
html {
    font-family: sans-serif;
}
div {
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    border: 1px solid #ccc;
    padding: 1rem ;
}
</style>