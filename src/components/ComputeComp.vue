<!-- eslint-disable vue/return-in-computed-property -->
<template>
    <div>
        <h1 class="text-decoration-underline">Computed Property</h1>
        <label for="input">Enter Word : </label>
        <input class="form-control" type="text" if="input" v-model="name">
        <button @click="evaluate" class="btn btn-primary mt-2">Reverse</button>
        <h4>Entered Word : {{ newname }}</h4>
        <h4>Reversed Word : {{ reversed }}</h4>
    </div>
</template>

<script setup>
import {ref,computed} from "vue"

const name=ref("")
const newname=ref("")

const evaluate=()=>{
    newname.value=name.value
    name.value=""
}
// eslint-disable-next-line vue/return-in-computed-property
const reversed=computed(()=>{
    return newname.value.split('').reverse().join('');
})

</script>