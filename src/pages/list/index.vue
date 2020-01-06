<template>
  <div>
    <view>
      <video src="cloud://hubuhmf-nzru0.6875-hubuhmf-nzru0-1300842120/vedioUrl/4.mp4" 
      style="margin:0 20px;height:130px;" poster object-fit:fill vslide-gesture-in-fullscreen
      enable-progress-gesture show-center-play-btn show-play-btn show-fullscreen-btn></video>
    </view>
  </div>
</template>

<script>
export default {
  data(){
    return {

    }
  },
  onLoad (options){
  //   // this.list = require('@/data/' + option.title + '.json')
    console.log(options)
  },
  methods: {
  }
}
</script>

<style scoped>

</style>>