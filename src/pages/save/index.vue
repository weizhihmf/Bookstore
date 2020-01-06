<template>
    <div>
        <i-panel title="收藏">
            <i-card title="听歌学英语" thumb="/static/images/ima.png" @click="goList">
                <view slot="content">内容不错,适合学习</view>
            </i-card>
        </i-panel>
    </div>
</template>

<script>
export default {
    data() {
        return {
            
        }
    },
    methods: {
        goList(){
            mpvue.navigateTo({ url:'../list/main' })
        }
    },
}
</script>

<style scoped>
.txt {
  font-size: 20px;
  margin-top: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>