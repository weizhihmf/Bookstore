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
          <image :src="img" class="imageSize" @tap="goTo"/>
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
        '/static/images/listen.png',
        '/static/images/speak.png',
        '/static/images/read.png'
      ],
      grids: [
        {title:"笔记",image:"/static/images/note.png","url":'../note/main'},
        {title:"收藏",image:"/static/images/save.png","url":'../save/main'},
        {title:"单词本",image:"/static/images/word.png","url":'../word/main'}
      ],
    }
  },
  methods: {
     handleChangeScroll(type){
        this.current = type.mp.detail.key
    },
     goUrl (title) {
       console.log(title)
       if(title==="收藏"){
         mpvue.navigateTo({ url:'../save/main' })
       }
        if(title==="笔记"){
         mpvue.navigateTo({ url:'../note/main' })
       }
       if(title==="单词本"){
         mpvue.navigateTo({ url:'../word/main' })
       }
      
    },
    goTo(){
      console.log(111)
      mpvue.navigateTo({
        url:('/pages/suggestions/main')
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