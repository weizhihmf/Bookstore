<template>
  <div>
    <i-tabs :current="current" scroll @change="handleChangeScroll">
      <i-tab key="0" title="推荐"></i-tab>
      <i-tab key="1" title="六级"></i-tab>
      <i-tab key="2" title="精选"></i-tab>
      <i-tab key="3" title="热门"></i-tab>
      <i-tab key="4" title="电影"></i-tab>
      <i-tab key="5" title="美剧"></i-tab>
      <i-tab key="6" title="动画"></i-tab>
      <i-tab key="7" title="演讲"></i-tab>
    </i-tabs>
    <swiper @change="changeView" :current="current" style="height:1150px;">
      <swiper-item v-for="(item,index1) in vedioUrl" :key="index1">
       <i-grid v-for="value in item" :key="value">
         <view>
             <video :src="value.url" style="height:130px;" :controls=controls poster object-fit=fill auto-pause-if-navigate @click="goToList"></video>
          <i-panel :title="value.remark">
      </i-panel> 
         </view> 
    </i-grid> 
    </swiper-item>
  </swiper>
  </div>
</template>

<script>
export default {
  data () {
    return {
      controls:false,
      current: "0",
      vedioUrl: [
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/1.mp4",remark:"音调可以"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/2.mp4",remark:"看影视学英语"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/3.mp4",remark:"看科技，励志"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/4.mp4",remark:"听小姐姐的歌曲学英语"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/5.mp4",remark:"适合学习"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/6.mp4",remark:"适合学习"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/7.mp4",remark:"介绍六级"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/8.mp4",remark:"精选篇"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/9.mp4",remark:"热门篇"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/10.mp4",remark:"电影篇"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/11.mp4",remark:"美剧篇"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/12.mp4",remark:"动画篇"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/13.mp4",remark:"演讲篇"}
        ]
      ]
    }
  },
  methods: {
    handleChangeScroll(type){
        this.current = type.mp.detail.key
    },

    changeView(e){
      this.current = e.mp.detail.current
    },
    goToList(event){
      console.log(event.mp)
      let url='../list/main?event=' + event.mp.target.dataset.eventid
      mpvue.navigateTo({ url:'../list/main?event=' + event.mp.target.dataset.eventid +'&strUrl=' + encodeURIComponent(JSON.stringify(url))})
    }
},
 created () {
   }
}
</script>

<style scoped>
</style>
