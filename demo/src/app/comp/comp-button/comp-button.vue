<!-- @author yutiangan -->
<!-- @email yutiangan@yangqianguan.com -->
<!-- @date 2018-09-17 15:58:04.555 -->
<!-- @desc generated by yqg-cli@0.2.2 -->

<template>

    <div class="comp-button">

        <div class="doc card">
            <div class="overview">
                <h2>
                    <span class="title">按钮</span>
                    <code>b-button</code>
                </h2>
                <b-md-view :md-text="MD.CompButtonOverview"/>
            </div>
            <div class="case">
                <h3>基本用法</h3>
                <b-md-view :md-text="MD.CompButtonBasic"/>

                <demo-box>
                    <div slot="code"><b-md-view :md-text="MD.CompButtonBasicCode"/></div>
                    <div slot="main" class="button-line">
                        <b-button @click="handleClick">来点我呀</b-button>
                        <b-button disabled @click="handleClick">Disabled</b-button>
                    </div>
                </demo-box>
            </div>

            <div class="case">
                <h3>主题</h3>
                <b-md-view :md-text="MD.CompButtonTheme"/>

                <demo-box>
                    <div slot="code"><b-md-view :md-text="MD.CompButtonThemeCode"/></div>
                    <div slot="main" class="button-line">
                        <b-button @click="handleClick">Normal</b-button>
                        <b-button theme="primary" @click="handleClick">Primary</b-button>
                        <b-button theme="danger" @click="handleClick">Danger</b-button>
                    </div>
                </demo-box>
            </div>

            <div class="case">
                <h3>大小</h3>
                <b-md-view :md-text="MD.CompButtonSize"/>

                <demo-box>
                    <div slot="code"><b-md-view :md-text="MD.CompButtonSizeCode"/></div>
                    <div slot="main" class="button-line">
                        <b-button size="sm" @click="handleClick">Normal</b-button>
                        <b-button theme="primary" size="sm" @click="handleClick">Primary</b-button>
                        <b-button theme="danger" size="sm" @click="handleClick">Danger</b-button>
                        <b-button size="sm" disabled @click="handleClick">Disabled</b-button>
                    </div>

                    <div slot="main" class="button-line">
                        <b-button @click="handleClick">Normal</b-button>
                        <b-button theme="primary" @click="handleClick">Primary</b-button>
                        <b-button theme="danger" @click="handleClick">Danger</b-button>
                        <b-button disabled @click="handleClick">Disabled</b-button>
                    </div>

                    <div slot="main" class="button-line">
                        <b-button size="lg" @click="handleClick">Normal</b-button>
                        <b-button theme="primary" size="lg" @click="handleClick">Primary</b-button>
                        <b-button theme="danger" size="lg" @click="handleClick">Danger</b-button>
                        <b-button size="lg" disabled @click="handleClick">Disabled</b-button>
                    </div>
                </demo-box>
            </div>

            <div class="case">
                <h3>形状</h3>
                <b-md-view :md-text="MD.CompButtonShape"/>

                <demo-box>
                    <div slot="code"><b-md-view :md-text="MD.CompButtonShapeCode"/></div>
                    <div slot="main" class="button-line">
                        <b-button size="sm" @click="handleClick">Normal</b-button>
                        <b-button shape="round" size="sm" @click="handleClick">Round</b-button>
                        <b-button shape="icon" size="sm" @click="handleClick">
                            <i class="b-icon-love"></i>
                        </b-button>
                        <b-button shape="simple" size="sm" @click="handleClick">Simple</b-button>
                        <b-button shape="link" size="sm" @click="handleClick">Link</b-button>
                    </div>
                    <div slot="main" class="button-line">
                        <b-button @click="handleClick">Normal</b-button>
                        <b-button shape="round" @click="handleClick">Round</b-button>
                        <b-button shape="icon" @click="handleClick">
                            <i class="b-icon-love"></i>
                        </b-button>
                        <b-button shape="simple" @click="handleClick">Simple</b-button>
                        <b-button shape="link" @click="handleClick">Link</b-button>
                    </div>
                    <div slot="main" class="button-line">
                        <b-button size="lg" @click="handleClick">Normal</b-button>
                        <b-button shape="round" size="lg" @click="handleClick">Round</b-button>
                        <b-button shape="icon" size="lg" @click="handleClick">
                            <i class="b-icon-love"></i>
                        </b-button>
                        <b-button shape="simple" size="lg" @click="handleClick">Simple</b-button>
                        <b-button shape="link" size="lg" @click="handleClick">Link</b-button>
                    </div>
                    <div slot="main" class="button-line">
                        <b-button shape="block" size="sm" @click="handleClick">Block</b-button>
                    </div>
                    <div slot="main" class="button-line">
                        <b-button shape="block" @click="handleClick">Block</b-button>
                    </div>
                    <div slot="main" class="button-line">
                        <b-button shape="block" size="lg" @click="handleClick">Block</b-button>
                    </div>
                </demo-box>
            </div>

            <div class="case">
                <h3>样式</h3>
                <b-md-view :md-text="MD.CompButtonStyle"/>

                <demo-box>
                    <div slot="code"><b-md-view :md-text="MD.CompButtonStyleCode"/></div>
                    <div slot="main" class="button-line">
                        <b-button @click="handleClick">Normal</b-button>
                        <b-button :btn-style="btnStyle" @click="handleClick">Customized</b-button>
                    </div>
                </demo-box>
            </div>

            <div class="case">
                <h3>表单一致性</h3>
                <b-md-view :md-text="MD.CompButtonConsistent"/>
            </div>

            <div class="case">
                <h3>API</h3>
                <b-md-view :md-text="MD.CompButtonAPI"/>
            </div>
        </div>
    </div>

</template>

<script type="text/babel">
    import MD from '../../../common/md';

    export default {
        name: 'CompButton',

        data() {
            return {
                MD,
                btnStyle: {
                    color: 'white',
                    backgroundColor: '#00bcd4',
                    border: 'none'
                }
            };
        },

        methods: {
            handleClick() {
                const vm = this;
                vm.$toast.info('按钮被点击!');
            }
        }
    };

</script>

<style lang="scss" scoped>
    .card {
        .b-button {
            @media screen and (max-width: 480px) {
                display: block;

                button {
                    width: 100%;
                }
            }
        }

        .case {
            .demo-box {
                .button-line {
                    margin: 10px;
                }
            }
        }
    }
</style>

