<script setup>
import ToastContent from "./ToastContent.vue"

defineProps({
    showToast: Boolean,
    showToastProgress: Boolean,
})
</script>

<template>
    <div class="toast" :class="{ active: showToast }">
        <ToastContent />
        <i class="fa-solid fa-xmark close" @click="$emit('close')"></i>
        <div class="progress" :class="{ active: showToastProgress }"></div>
    </div>
</template>

<style lang="scss" scoped>
.toast {
    position: absolute;
    top: 25px;
    right: 30px;
    border-radius: 12px;
    background-color: #2e2e3f;
    padding: 20px 35px 20px 25px;
    box-shadow: 0px 6px 20px -5px rgba(0, 0, 0, 0.5);
    border: 1px solid #444;
    transform: translateX(calc(100% + 30px));
    transition: all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.35);

    &.active {
        transform: translateX(0%);
    }

    .close {
        position: absolute;
        top: 10px;
        right: 15px;
        padding: 5px;
        cursor: pointer;
        opacity: 0.7;
        color: #fff;

        &:hover {
            opacity: 1;
        }
    }

    .progress {
        position: absolute;
        bottom: 0;
        left: 0;
        height: 3px;
        width: 100%;
        background-color: #444;
        overflow: hidden;

        &:before {
            content: "";
            position: absolute;
            bottom: 0;
            right: 0;
            height: 100%;
            width: 100%;
            background-color: #ffc75f;
        }

        &.active:before {
            animation: progress 5s linear forwards;
        }
    }
}
</style>
