<script setup>
import ChildComponent from './ChildComponent.vue';
import { ref } from 'vue';
let message = ref('Message From Parent')

function updateMessage(receivedMessage) {
    message.value = receivedMessage
}
</script>

<template>
    <div class="flex justify-center items-center min-h-screen flex-col mx-auto text-center">
        <div class="p-10 border border-slate-400 w-[400px] sm:w-[600px]">
            <h1 class="text-3xl font-bold mb-5 border-b border-slate-400 pb-2">Parent Component</h1>
            <h3 class="text-2xl mb-5 text-center">{{ message }}</h3>
            <button class="mb-10 border border-blue-500 bg-blue-500 hover:bg-blue-600 text-white px-10 py-2"
                @click="message = 'Message From Parent'">Reset From parent</button>
            <child-component class="p-5 border border-slate-400" :message="message" @messageEmitted="updateMessage" />
        </div>
    </div>
</template>

<style scoped></style>