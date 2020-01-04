<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:180px"
    >
      <block v-for="img in imgUrls" :key="img">
        <swiper-item>
          <image :src="img" class="imageSize" @click="goTo"/>
        </swiper-item>
      </block>
    </swiper>
     <i-grid i-class="no-border">
    <i-grid-item @click="goUrl(grid.title)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>  
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
  </i-grid>
  <i-tabs :current="current" scroll @change="handleChangeScroll">
      <i-tab key="0" title="学习记录"></i-tab>
      <i-tab key="1" title="离线课程"></i-tab>
  </i-tabs>
  <swiper @change="changeView" :current="current" style="height:1150px;">
      <swiper-item v-for="(item,index1) in vedioUrl" :key="index1">
       <i-grid v-for="value in item" :key="value">
         <view>
             <video :src="value.url" style="height:130px;"></video>
          <i-panel :title="value.remark">
      </i-panel> 
         </view> 
    </i-grid> 
    </swiper-item>
  </swiper>
  <i-card title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
    <view slot="content">内容不错</view>
    <view slot="footer">尾部内容</view>
</i-card>
<i-card title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
    <view slot="content">内容不错</view>
    <view slot="footer">尾部内容</view>
</i-card>
<i-card title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
    <view slot="content">内容不错</view>
    <view slot="footer">尾部内容</view>
</i-card>
  </div>
</template>

<script>
export default {
  data(){
    return {
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
      current: "0",
       imgUrls: [
        'cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/images/listen.png',
        'cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/images/speak.png',
        'cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/images/read.png'
      ],
      grids: [],
    }
  },
  created() {
    const db = wx.cloud.database({env:'hubuhmf-nzru0'})
    db.collection('grids').get().then(
      res => {
        console.log(res.data)
        this.grids = res.data
      }
    )
  },
  methods: {
     handleChangeScroll(type){
        this.current = type.mp.detail.key
    },
     goUrl (title) {
       if(title==="笔记"){
         mpvue.navigateTo({ url:'../note/main' })
       }
        if(title==="收藏"){
         mpvue.navigateTo({ url:'../save/main' })
       }
       if(title==="单词本"){
         mpvue.navigateTo({ url:'../word/main' })
       }   
    },
    goTo(){
      mpvue.navigateTo({
        url:'/pages/note/main'
    })
  }
}
}
</script>

<style scoped>
.imageSize{
  width: 90%;
  margin:0 5%; 
  border: 1px solid gainsboro;
  border-radius: 10px;
}
div >>> .no-border {
  border-width: 0pt;
}
</style>>