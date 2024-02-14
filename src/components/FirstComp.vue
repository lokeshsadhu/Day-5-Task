<!-- eslint-disable vue/require-v-for-key -->
<template>
    <div>
        <h1 class="text-decoration-underline">First Component</h1>
        <h3>{{ text }}</h3>
        <ul v-for="(game, index) in games" :key="index">
            <li>{{ game.title }} : {{ game.year }} </li>
            <div><button @click.prevent="$emit('editGame',game.title)" class="btn btn-secondary mt-2">Edit Title</button></div>
        </ul>
        
    </div>
</template>

<script setup>

defineProps(["text","games"])
</script>