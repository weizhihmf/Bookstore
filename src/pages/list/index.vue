<template>
  <div>
    <view>
      <video :src="src "
      style="margin:0 20px;height:130px;" poster object-fit:fill vslide-gesture-in-fullscreen
      enable-progress-gesture show-center-play-btn show-play-btn show-fullscreen-btn></video>
    </view>
  </div>
</template>

<script>
export default {
  data(){
    return {
      src:''
    }
  },
  onLoad (options){
    console.log(options)
    let jsonParam = JSON.parse(decodeURIComponent(options.strUrl))
    console.log(jsonParam);
    this.src = jsonParam
  },
  methods: {
  }
}
</script>

<style scoped>

</style>>