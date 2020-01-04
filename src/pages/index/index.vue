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
             <video :src="value.url" style="height:130px;"></video>
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
      current: "0",
      vedioUrl: [
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/1.mp4",remark:"音调可以"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/2.mp4",remark:"看影视学英语"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/3.mp4",remark:"看科技，励志"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/4.mp4",remark:"听小姐姐的声音学英语"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/5.mp4",remark:"介绍5"},
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/6.mp4",remark:"介绍6"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/7.mp4",remark:"介绍1"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/8.mp4",remark:"介绍1"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/9.mp4",remark:"介绍1"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/10.mp4",remark:"介绍1"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/11.mp4",remark:"介绍1"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/12.mp4",remark:"介绍1"}
        ],
        [
          {url:"cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/13.mp4",remark:"介绍1"}
        ]
      ]
    }
  },
  methods: {
    handleChangeScroll(type){
        this.current = type.mp.detail.key
      // let url='../list/main?type=' + type.mp.detail.key
      // mpvue.navigateTo({ url })
    },

    changeView(e){
      this.current = e.mp.detail.current
    },

    created () {
   }
}
}
</script>

<style scoped>
</style>
