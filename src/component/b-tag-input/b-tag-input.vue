<!-- @author smwang -->
<!-- @email smwang@yangqianguan.com -->
<!-- @date 2018-11-06 15:56:15.314 -->
<!-- @desc generated by yqg-cli@0.3.6 -->

<template>

    <div ref="wrap" class="yqg-tag-input">
        <div
            :class="{'content-container-active': isActive}"
            class="content-container"
            @click="onContainerClick"
        >
            <div v-for="(tag, index) in value" :key="tag" class="tag">
                <div class="tag-area">{{ tag }}</div>
                <i class="b-icon-cross close" @click.stop="onDeleteTag(index)"></i>
            </div>
            <div class="input-area">
                <span ref="shadowSpan" class="input-display">{{ currText }}</span>
                <input
                    ref="tagInput"
                    :value="currText"
                    :style="{width: inputWidth + 'px'}"
                    type="text"
                    class="tag-input"
                    autocomplete="false"
                    @input="onInput"
                    @focus="setActive"
                    @blur="cancelActive"
                    @keydown.enter="onPressEnter"
                    @keydown.delete="onDelete"
                >
            </div>
        </div>
    </div>

</template>

<script type="text/babel">

    export default {
        name: 'BTagInput',

        props: {
            value: {
                type: Array,
                default: () => ([])
            }
        },

        data() {
            return {
                currText: '',
                isActive: false,
                inputWidth: 50
            };
        },

        methods: {
            onContainerClick() {
                const vm = this;

                vm.$refs.tagInput.focus();
            },

            setActive() {
                this.isActive = true;
            },

            cancelActive() {
                this.isActive = false;
            },

            onPressEnter() {
                const vm = this;
                if (vm.value.includes(vm.currText)) {
                    vm.$toast.error(`已经存在值"${vm.currText}"`);
                    return;
                }
                if (vm.currText) {
                    vm.$emit('input', [...vm.value, vm.currText]);
                }
                setTimeout(() => (vm.currText = ''), 0);
            },

            onDeleteTag(index) {
                const vm = this;
                vm.$emit('input', [...vm.value.slice(0, index), ...vm.value.slice(index + 1)]);
            },

            onInput(event) {
                const vm = this;
                vm.updateInputElement(event.target.value);
            },

            onDelete() {
                const vm = this;
                if (vm.currText) return;
                vm.$emit('input', vm.value.slice(0, vm.value.length - 1));
            },

            updateInputElement(text = '') {
                const vm = this;

                vm.currText = text;
                vm.$nextTick(() => {
                    const shadowSpanWidth = vm.$refs.shadowSpan.clientWidth + 50;
                    const maxWidth = vm.$refs.wrap.clientWidth;

                    vm.inputWidth = Math.min(shadowSpanWidth, maxWidth);
                });

            }
        }
    };

</script>
