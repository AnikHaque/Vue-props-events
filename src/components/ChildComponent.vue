<script setup>
defineProps(['message'])
defineEmits(['messageEmitted'])
</script>

<template>
    <div>
        <h2 class="text-xl font-bold mb-3 pb-2 border-b border-slate-400">Child Component</h2>
        <p class="text-xl mb-5 text-center">{{ message }}</p>
        <button class="border border-blue-500 px-10 py-2 bg-blue-500 hover:bg-blue-600 text-white"
            @click="$emit('messageEmitted', 'Modified Parent Message from child')">Modify parent message from child</button>
    </div>
</template>

<style scoped></style>