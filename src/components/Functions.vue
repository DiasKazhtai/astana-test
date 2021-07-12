<template>
    <div class="Functions">
        <Sidebar @pickFunction="pickFunction" />
        <div class="Functions__wrapper Functions__wrapper_column">
            <div class="Functions__header">Function {{ functionType }}</div>
            <Function1 v-if="functionType === 1" />
            <Function2 v-if="functionType === 2" />
            <Function3 v-if="functionType === 3" />
        </div>
    </div>
</template>

<script>
import Sidebar from '@/components/Sidebar';
import Function1 from '@/components/Function1';
import Function2 from '@/components/Function2';
import Function3 from '@/components/Function3';
export default {
    data() {
        return {
            functionType: '',
        }
    },
    components: {
        Sidebar,
        Function1,
        Function2,
        Function3,
    },
    methods: {
        pickFunction(name) {
            this.functionType = Number(name[name.length - 1])
            console.log(this.functionType);
        }
    }
}
</script>


<style lang="scss">
    .Functions {
        display: flex;

        &__header {
            width: 100%;
            height: 100px;
            border-bottom: 1px solid #d1d3d6;
            padding: 15px 15px;
            font-size: 32px;
            font-weight: 900;
        }

        &__wrapper {
            display: flex;
            width: 100%;

            &_column {
                flex-direction: column;
            }
        }
    }
</style>