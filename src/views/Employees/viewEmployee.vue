<template>
    <div>
      <Filter v-bind:msg="msg" v-bind:message="message"></Filter>
        <Table v-bind:tableHeaders="tableHeaders" v-bind:data="data"></Table>
    </div>
</template>

<script>
import Table from '@/components/Table';
import Filter from '@/components/Filter';
export default {
    name: 'ViewEmployee',
    components: {
        Table,
        Filter,
    },
    data() {
        return {
            data: [],
            tableHeaders: [],
            msg: 'Filter Employees by ID:',
            message: 'Enter Employee Id',
        };
    },
    methods: {
        async getData(param = '') {
            const response = await fetch('https://fbc.exitest.com/employee' + param);
            if (response.ok) {
                const data = await response.json();
                return data;
            } else {
                return console.log('HTTP-Error: ' + response.status);
            }
        },
    },
    async mounted() {
        this.data = Object.values(await this.getData());
        if (this.data.length) {
            this.tableHeaders = Object.keys(this.data[0]);
        } else {
            this.tableHeaders = ['Data is not present!'];
        }
    },
};
</script>

<style scoped></style>
