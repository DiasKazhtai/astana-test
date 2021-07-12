<template>
    <div class="Function2">
        <div class="Function2__title">Входные данные</div>
        <div class="Function2__wrapper">
            <my-input v-model="firstValue" :label="'Строка А'"/>
        </div>
        <div class="Function2__result">Результат</div>
        <div class="Function2__value">{{ getResult }}</div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            firstValue: '',
        }
    },
    computed: {
        getResult() {
            if(this.firstValue.split('').reverse().join('').toLowerCase() === this.firstValue.toLowerCase()
             && this.firstValue.length > 0) {
                return 'Да';
            };
            return 'Нет';
        }
    }
}
</script>



<style lang="scss">
    .Function2 {
        width: 200%;
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
            font-size: 20px;
            font-weight: bold;
        }
    }
</style>