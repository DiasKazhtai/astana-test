<template>
    <div class="Function3">
        <div class="Function3__title">Входные данные</div>
        <div class="Function3__wrapper">
            <my-input v-model="firstValue" :label="'Строка А'"/>
        </div>
        <div class="Function3__result">Результат</div>
        <div class="Function3__value">{{ firstValue }}</div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            firstValue: '',
        }
    },
}
</script>



<style lang="scss">
    .Function3 {
        width: 300%;
        padding: 30px 40px;

        &__title {
            margin-bottom: 30px;
        }

        &__title, &__result {
            font-size: 26px;
            color: #468cdd;
            font-weight: 900;
        }

        &__wrapper {
            display: flex;
            margin-bottom: 30px;
        }

        &__result {
            margin-bottom: 20px;
        }

        &__value {
            font-size: 25px;
            font-weight: bold;
            color: red;
        }
    }
</style>