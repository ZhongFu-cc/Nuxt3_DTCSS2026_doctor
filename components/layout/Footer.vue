<template>
    <footer class="footer-section">
        <div class="footer-box">
            <p>大林慈濟醫院 心臟血管外科</p>
            <p>院址：622 嘉義縣大林鎮民生路二號</p>
            <p>電話：05-264-8000</p>
        </div>
    </footer>
</template>
<script lang="ts" setup>
import Title from './Title.vue';
</script>
<style lang="scss" scoped>
.footer-section {
    background: linear-gradient(to right, #ee9ab9 0%, #383587 70%);
    background-size: cover;
    padding: 2rem 0;

    .footer-box {
        display: flex;
        flex-direction: column;
        width: 70%;
        color: white;
        margin: 0 auto;
        font-size: 1.1rem;
        font-weight: bold;
    }
}
</style>