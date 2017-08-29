<template>
    <div>
        <btn @click.native="onClick">打开窗口</btn>
        <dialog-el title="窗口标题" :isShow.sync="isShow" >
            <div slot="body">窗口内容</div>
            <div slot="footer">
                <btn type="primary" color="orange" @click.native.stop.prevent="onConfirm">确认</btn> <btn  @click.native.stop.prevent="onCancel">取消</btn>
            </div>
        </dialog-el>
    </div>
</template>

<style lang="less">
</style>

<script>

    import btn from 'pcadmin-button';
    import dialogEl from "../src/dialog.vue";

    export default {
        data(){
            return {
                isShow : false
            }
        },
        mounted(){

        },
        methods: {

            onClick(){
                console.log('on click..........');
                this.isShow =  true;
            },
            onConfirm(){
                console.log('onConfirm');
                this.isShow =  false;
            },
            onCancel(){
                console.log('on cancel....');
                this.isShow =  false;
            }
        },
        components: {
            btn,
            dialogEl
        }
    }
</script>

