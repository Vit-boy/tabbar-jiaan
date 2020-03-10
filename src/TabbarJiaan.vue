<template>
    <div class="tabbar-jiaan">
        <div :class="cur == index ? 'menu evl' : 'menu'" v-for="(item, index) in list" @click="handleMenu(index)">
            <img :src="item.icon" class="icon" />
            <img :src="item.iconSelect" class="iconSelect" />
            <div class="text">{{item.text}}</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'TabbarJiaan',
        props: ['cur', 'list'],
        methods: {
            handleMenu(index) {
                this.$emit('handleMenu', index)
            }
        }
    }
</script>

<style scoped>
    .tabbar-jiaan {
        position: fixed;
        width: 100%;
        height: 1rem;
        background-color: #fff;
        bottom: 0;
        display: flex;
        justify-content: space-between;
        align-items: center;
        box-shadow: 0rem -0.06rem 0.27rem rgba(0, 0, 0, 0.1);
        z-index: 999;
    }
    .tabbar-jiaan .menu {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: column;
        flex: 1;
    }
    .tabbar-jiaan .menu .icon {
        display: block;
        height: 0.45rem;
        width: auto;
    }
    .tabbar-jiaan .menu .iconSelect {
        display: block;
        height: 0.45rem;
        width: auto;
        display: none;
    }
    .tabbar-jiaan .menu .text {
        font-size: 0.18rem;
        color: #333333;
        opacity: 0.8;
        line-height: 0.25rem;
        margin-top: 0.05rem;
    }
    .tabbar-jiaan .menu.evl .icon {
        display: none;
    }
    .tabbar-jiaan .menu.evl .iconSelect {
        display: block;
    }
    .tabbar-jiaan .menu.evl .text {
        color: #36b082;
    }
</style>