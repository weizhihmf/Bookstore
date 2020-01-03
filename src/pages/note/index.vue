<template>
    <div>
        <i-panel title="笔记">
            <i-input :value=" value" placeholder="赶快写下你的笔记吧"/>
        </i-panel>
    </div>
</template>

<script>
export default {
    data() {
        return {
            value:""
        }
    },
}
</script>

<style scoped>

</style>