<template>
    <h1>Please fill this form to add an employee...</h1>
    <keep-alive>
    <Form />
    </keep-alive>
</template>

<script>
import Form from '@/components/addForm';

export default {
    name: 'AddEmployee',
    components: {
        Form,
    },
};
</script>

<style scoped>
h1 {
    background: -webkit-repeating-radial-gradient(yellow, white);
    padding: 15px;
}
</style>
