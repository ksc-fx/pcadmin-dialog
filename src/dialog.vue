<template>
    <transition name="container-fade"  >
    <div class="dialog-container" v-show="isShow" >
        <div class="dialog-wrapper" @click="onClose">
            <transition name="fade">
            <div class="dialog" @click.stop.prevent=""  v-show="isShow">
                <div class="dialog-header">标题</div>
                <div class="dialog-body">
                      <slot name="body"> 我是内容 </slot>
                </div>
                <div class="dialog-footer">
                    <slot name="footer"> 我是footer </slot>
                </div>
            </div>
            </transition>
        </div>
        <div class="v-modal"></div>
    </div>
    </transition>
</template>
<style lang="less" scoped>

    @import '~pcadmin-base/src/css/var.less';

    .fade-leave-active,.fade-enter-active {
        transition: all .3s ease;
    }

    .fade-enter, .fade-leave-to{
        transform: translateY(-50px);
        opacity: 0;
    }


    .container-fade-enter-active, .container-fade-leave-active {
        transition: all .3s ease;
    }
    .container-fade-enter,.container-fade-leave-to{
        opacity: 0;
    }


    .dialog-container{

        .v-modal {
            position: fixed;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            opacity: .5;
            background: #000;
            z-index: 100;
        }
        .dialog-wrapper {
            position: fixed;
            left: 0;
            right:0;
            height:100vh;
            margin: auto;
            z-index: 101;
            display: flex;
            align-items: center;
            justify-content: center;

            .dialog{
                padding:15px;
                background: #fff;
                border-radius: 2px;
                .dialog-header{
                    font-size:16px;
                    font-weight: 400;
                }
                .dialog-body{
                    padding:20px;
                    font-size:14px;
                    color:#48576a;
                }
                .dialog-footer{
                    padding:10px 20px 15px;
                    text-align:right;
                }
            }
        }
    }
</style>
<script>
    export default{
        name: "dialog",
        props: {
            title: {
                type: String,
                default: 'title'
            },
            isShow: {
                type:Boolean,
                default:false
            }
        },
        data(){
            return {
            }
        },
        watch: {
            isShow(newVal,oldVal){
                if(newVal){
                    document.body.style.overflow = 'hidden';
                }else{
                    document.body.style.overflow = '';
                }
            }
        },
        computed: {},
        mounted() {

        },

        methods: {
            /*
            onConfirm(event){
                this.$emit('confirm', event);
            },
            onCancel(){
                this.$emit('cancel', event);
            },
            */
            onClose(event) {
                this.$emit('update:isShow', false)
                this.$emit('close', event);
            }
        },
        components:{
        }
    }
</script>
