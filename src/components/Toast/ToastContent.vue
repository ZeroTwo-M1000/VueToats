<script setup></script>

<template>
    <div class="toast-content">
        <i class="fas fa-solid fa-check check"></i>

        <div class="message">
            <span class="text text-1">Success</span>
            <span class="text text-2">Your changes has been saved</span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.toast-content {
    display: flex;
    align-items: center;

    .check {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 35px;
        min-width: 35px;
        background-color: #ffc75f;
        color: #fff;
        font-size: 20px;
        border-radius: 50%;
        border: 2px solid #333;
    }

    .message {
        display: flex;
        flex-direction: column;
        margin: 0 20px;

        .text {
            font-size: 16px;
            font-weight: 400;
            color: #cccccc;

            &.text-1 {
                font-weight: 600;
                color: #ffffff;
            }
        }
    }
}
</style>
