<template>
    <div>
        <h1>Login Page</h1>
        <label for="input">Enter E-mail : </label>
        <input class="form-control" type="text" if="input" v-model="loginemail">
        <label for="input">Enter phone : </label>
        <input class="form-control" type="text" if="input" v-model="loginphone">
        <button class="btn btn-success mt-2" @click='$emit("login",loginemail,loginphone)'>Login</button>
    </div>
</template>

<script setup>
import {ref} from "vue"

const loginemail=ref("")
const loginphone=ref("")
</script>