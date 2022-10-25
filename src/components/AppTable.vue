<template>
    <table class="table">
        <thead>
            <tr>
                <td class="col header-col">ID</td>
                <td class="col header-col">NAME</td>
                <td class="col header-col">LASTNAME</td>
                <td class="col header-col">AGE</td>
            </tr>
        </thead>
        <tbody>
            <template v-if="appData == null">
                <tr class="row" v-for="(d, index) in data" :key="index" @click="$emit('clickRow', d.id)">
                    <th class="col data-col">{{d.id}}</th>
                    <th class="col data-col">{{d.name}}</th>
                    <th class="col data-col">{{d.lastName}}</th>
                    <th class="col data-col">{{d.age}}</th>
                </tr>
            </template>
            <template v-else>
                <tr class="row" v-for="(d, index) in appData" :key="index" @click="$emit('clickRow', d.id)">
                    <th class="col data-col">{{d.id}}</th>
                    <th class="col data-col">{{d.name}}</th>
                    <th class="col data-col">{{d.lastName}}</th>
                    <th class="col data-col">{{d.age}}</th>
                </tr>
            </template>
        </tbody>
    </table>    
</template>

<script>
import data from "../assets/data";

export default {
    name: "AppTable",
    props: {
        appData: Array,
    },
    data() {
        return {
            data: data
        }
    }
}
</script>

<style>
    .table {
        margin-bottom: 16px;
        border: 2px solid red;
    }
    .col {
        border: 2px solid red;
    }
    .header-col {
        font-size: 20px;
        font-weight: 700;
    }
    .data-col {
        font-weight: 400;
    }
</style>
