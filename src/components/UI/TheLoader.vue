<template>
    <div class="bg-loader">
        <h3>loading</h3>
        <div class="loading-loader">
            <img src="@/src/assets/loader.png" alt="">
        </div>
    </div>
</template>

<style scoped>
    @keyframes loading {
        0%{
            transform: rotate(0);
        }
        50%{
            transform: rotate(180);
        }
        100%{
            transform: rotate(359.9999);
        }
    }
</style>