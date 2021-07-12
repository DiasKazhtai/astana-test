<template>
    <div class="Sidebar" :class="{ Sidebar__active: isActive}">
        <div class="Sidebar__title" @click="sidebarHandler">
            <span></span>
            <p v-if="!isActive">Functions</p>
        </div>
        <div class="wrapper" v-if="!isActive" @click="pickFunction($event)">
            <div class="Sidebar__item">Function 1</div>
            <div class="Sidebar__item">Function 2</div>
            <div class="Sidebar__item">Function 3</div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isActive: true,
        }
    },
    methods: {
        sidebarHandler() {
            this.isActive = !this.isActive;
        },
        pickFunction(e) {
            this.$emit('pickFunction', e.target.innerHTML);
        }
    }
}
</script>

<style lang="scss">
.Sidebar {
    width: 30%;
    height: 100vh;
    background: #dfe0e2;
    transition: 0.2s;

    &__title {
        width: 100%;
        height: 100px;
        background: #478ad7;
        display: flex;
        justify-content: center;
        align-items: center;
        color: white;
        font-size: 25px;
        position: relative;
        cursor: pointer;

        @media (max-width: 768px) {
            display: none;
        }

        &::before,
        &::after,
        span {
            content: '';
            display: block;
            width: 40px;
            height: 2px;
            background-color: white;
            position: absolute;
        }

        &::before {
            left: 35px;
            top: 42px;
        }

        &::after {
            left: 35px;
            top: 56px;;
        }

        span {
            left: 35px;
        }
    }

    &__item {
        cursor: pointer;
        width: 100%;
        height: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 18px;
        font-weight: bold;

        &:hover {
            background-color: #c1c4c8;
        }
    }

    &__active {
        width: 10%;
    }
}
</style>