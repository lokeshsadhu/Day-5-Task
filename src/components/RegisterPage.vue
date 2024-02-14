<template>
    <div>
        <h1>Register</h1>
        <label for="input">Enter E-mail : </label>
        <input class="form-control" type="text" if="input" v-model="email">
        <label for="input">Enter phone : </label>
        <input class="form-control" type="text" if="input" v-model="phone">
        <button class="btn btn-warning mt-2" @click='$emit("register",email,phone)'>Register</button>
    </div>
</template>

<script setup>
import {ref} from "vue"

const email=ref('')
const phone=ref('')
</script>