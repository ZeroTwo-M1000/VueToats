<template>
    <div>
        <Toast @close="closeToastClick" :showToast="showToast" :showToastProgress="showToastProgress" />
        <Btn @click="showToastClick" />
    </div>
</template>

<script setup>
import { ref } from "vue"
import Toast from "./components/Toast/Toast.vue"
import Btn from "./components/Btn.vue"

const showToast = ref(false)
const showToastProgress = ref(false)

const showToastClick = () => {
    showToast.value = !showToast.value
    showToastProgress.value = true

    setTimeout(() => {
        showToast.value = false
    }, 5000)

    setTimeout(() => {
        showToastProgress.value = false
    }, 5300)
}

const closeToastClick = () => {
    showToast.value = false
    showToastProgress.value = false
}
</script>

<style lang="css">
.toast.active ~ button {
    pointer-events: none;
}
</style>
