<template>
    <div>
        <h1 class="text-decoration-underline">Watcher Property</h1>
        <div class="d-flex flex-row">
            <button @click="count++" class="btn btn-success mt-0">Increase</button>
            <h1>{{ count }}</h1>
            <button @click="count--" class="btn btn-danger ml-2 mt-0">Decrease</button>
        </div>
    </div>
        
</template>

<script setup>
import {ref,watch} from "vue"

const count = ref(0)

watch(count,(oldvalue,newvalue)=>{
    if(count.value>5){
        alert("The value Exceeded 5")
    }
},{immediate:true})
</script>