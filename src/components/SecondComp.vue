<template>
    <div>
    <h1 class="text-decoration-underline">Second Component</h1>
    <form @submit.prevent="onSubmit">
        <label>Enter name : </label>
        <input class="form-control" type="text" v-model="username">
        <label>Password : </label>
        <input class="form-control" type="password" v-model="password">
        <button @click="$emit('buttonClicked',username,password)" class="btn btn-primary mt-2">Submit</button>
    </form>  
    </div>
</template>

<script setup>
import {ref} from "vue"

const username=ref("")
const password=ref("")

defineEmits(["buttonClicked"])
</script>