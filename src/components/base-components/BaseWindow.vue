<template>
    <div class="base-window">
        <div class="window-header">
            <button class="btn-close"></button>
        </div>
        <slot></slot>
    </div>
</template>

<style scoped>
    .base-window{
        width: 30%;
        height: 40%;
        background-color: white;
    }
</style>