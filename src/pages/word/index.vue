<template>
    <div>
        <i-panel title="单词本">
           <i-cell-group>
            <i-cell title="beam\n  n.横梁；光线；电波；船宽；"></i-cell>
            <i-cell title="discharge\n  v.准许（某人）离开；释放；排出；放电；"></i-cell>
            <i-cell title="dignity\n  n.尊严；高贵；"></i-cell>
            <i-cell title="muddy\n  adj.泥泞的；模糊的；混乱的；"></i-cell>
            <i-input :value="value" autofocus placeholder="写下你的学习单词吧" @click="addWords"/>
            </i-cell-group>
        </i-panel>
    </div>
</template>

<script>
export default {
    data() {
        return {
            value:''
        }
    },
    methods: {
        addWords(e){
            console.log(e)
            this.value=e.mp.detail.value
        }
    },
}
</script>

<style scoped>

</style>