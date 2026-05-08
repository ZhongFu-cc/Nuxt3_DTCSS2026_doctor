<template>
    <ClientOnly>
        <div class="menu-container">

            <div class="logo-container">
                <nuxt-link class="logo-link" :to="localPath('/')">
                    <div class="logo-image-box">
                        <img class="logo" src="/img/logo.png" alt="DTCSS Logo" />
                    </div>
                </nuxt-link>
            </div>


            <div class="menu-box">
                <img class="translation-icon" src="@/assets/img/translation1.svg" alt="earth icon"
                    @click="translationMenuState.toggleMenu" />

                <div class="sub-menu-box last-sub-menu-box" v-if="translationMenuState.isOpen">
                    <el-button @click="setLang('zh')">繁體中文</el-button>
                    <el-button @click="setLang('en')">English</el-button>
                </div>
            </div>
        </div>
    </ClientOnly>
</template>

<script lang="ts" setup>

const isLogin = useState('isLogin', () => false)

const localPath = useLocalePath()
const { t, setLocale } = useI18n()


const setLang = (lang: string) => {
    translationMenuState.value.isOpen = false;
    localStorage.setItem('lang', lang);
    setLocale(lang);
}



const translationMenuState = ref({
    isOpen: false,
    toggleMenu: () => {
        translationMenuState.value.isOpen = !translationMenuState.value.isOpen
    }
})




</script>
<style lang="scss" scoped>
.menu-container {
    background-color: #19254e;
    width: 100%;
    height: auto;
    display: flex;
    justify-content: space-around;
    align-items: center;

    .logo-container {
        width: 30%;

        .logo-image-box {
            width: 27rem;
            height: 100%;
            .logo {
                width: 27rem;
                height: 100%;
                object-fit: contain;
            }
        }
    }

    .menu-box {
        width: 30%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        position: relative;

        .translation-icon {
            width: 1.5rem;
            height: 1.5rem;
            cursor: pointer;
        }

    }
}
</style>