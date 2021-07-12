<template>
    <div class="Function1">
        <div class="Function1__title">Входные данные</div>
        <div class="Function1__wrapper">
            <my-input v-model="firstValue" :label="'Строка А'" class="Function1__input" />
            <my-input  v-model="secondValue" :label="'Строка Б'" />
        </div>
        <div class="Function1__result">Результат</div>
        <div class="Function1__value">{{ getResult }}</div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            firstValue: '',
            secondValue: '',
            sum: 0,
        }
    },
    computed: {
        getResult() {
            return this.sum; 
        }
    }
}
</script>



<style lang="scss">
    .Function1 {
        width: 100%;
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

        &__input {
                margin-right: 20px;
        }

        &__result {
            margin-bottom: 20px;
        }

        &__value {
            font-size: 20px;
            font-weight: bold;
        }
    }
</style>