<template>
        <section>
            <form @submit.prevent="submitData">
            <input type="text" placeholder="Your Name" v-model="enteredName" />
            <input type="age" placeholder="Your Age" v-model="enteredAge" />
            <button>Add User</button>
            </form>
            </section>

            
</template>

<script>


export default {
    emits: ['add-user'],
    data() {
        return {
            enteredName: '',
            enteredAge: ''
        };
    },
    methods: {
        submitData() {
            this.$emit('add-user', this.enteredName, this.enteredAge);
        }
    }
};
</script>
