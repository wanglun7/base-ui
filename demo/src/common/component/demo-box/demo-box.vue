<!-- @author Kyles Light -->
<!-- @email likelakes07@gmail.com -->
<!-- @date 2018-07-28 21:35:03.950 -->
<!-- @desc generated by yqg-cli@0.1.13 -->

<template>

    <div class="demo-box">
        <div class="action">
            <b-button shape="icon" @click="visible = !visible">
                <i class="b-icon-code"></i>
            </b-button>
        </div>

        <transition name="slide-fade">
            <div v-if="visible" class="demo-code">
                <slot name="code"></slot>
            </div>
        </transition>

        <div class="main">
            <slot name="main"></slot>
        </div>

        <div v-if="$slots.output" class="output">
            <slot name="output"></slot>
        </div>
    </div>

</template>

<script type="text/babel">

    export default {
        name: 'DemoBox',

        data() {
            return {
                visible: false
            };
        }
    };

</script>

<style lang="scss" rel="stylesheet/scss">

    @import "../../../../../src/style/variables.scss";

    .demo-box {
        box-sizing: border-box;
        margin: 0 20px 40px;
        padding: 10px 20px 0;
        border: 1px solid $gray-light;
        border-radius: 3px;

        .action {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            margin: -10px -20px 0;
            padding: 10px;
            background-color: $gray-lighter;
            box-shadow: $standard-box-shadow;
        }

        .demo-code {
            margin: 0 -20px 15px;
            box-shadow: $standard-box-shadow;

            .b-md-view {
                padding: 0;

                pre {
                    padding: 25px;
                    margin-bottom: 0;
                    border: none;
                    border-bottom: 1px solid $gray-light;
                    background-color: lighten($gray-lighter, 3);
                }
            }
        }

        .main {
            margin: 30px 0;

            p {
                code {
                    padding: 0 5px;
                    border-radius: 3px;
                    background-color: $gray-lighter;
                    color: $primary-dark;
                    font-family: Menlo, Courier, monospace;
                }
            }
        }

        .output {
            margin: 30px -21px 0;
            padding: 10px 20px;
            border-bottom-left-radius: 3px;
            border-bottom-right-radius: 3px;
            background-color: $gray-dark;
            color: $white;
            font-family: monospace;
            font-size: 12px;
        }
    }

</style>
