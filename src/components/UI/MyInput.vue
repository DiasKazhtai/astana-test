<template>
    <div class="MyInput">
        <div class="MyInput__label">{{ label }}</div>
        <input @input="updateInput" type="text" class="MyInput__input">
    </div>
</template>

<script>
export default {
    name: 'myInput',
    props: {
        label: {
            type: String,
        },
        modelValue: [String, Number],
    },
    methods: {
        updateInput(event) {
            this.$emit('update:modelValue', event.target.value);
        },
    },
}
</script>

<style lang="scss">
    .MyInput {
        &__label {
            font-size: 20px;
            color: #7a8694;
            margin-bottom: 10px;
        }

        &__input {
            width: 250px;
            height: 50px;
            border-radius: 6px;
            padding: 10px 15px;
            font-size: 18px;
        }
    }
</style>