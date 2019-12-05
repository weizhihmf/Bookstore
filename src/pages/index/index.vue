<template>
  <div>
    <i-tabs :current="current_scroll" scroll @change="handleChangeScroll">
      <i-tab key="0" title="推荐"></i-tab>
      <i-tab key="1" title="六级"></i-tab>
      <i-tab key="2" title="精选"></i-tab>
      <i-tab key="3" title="热门"></i-tab>
      <i-tab key="4" title="电影"></i-tab>
      <i-tab key="5" title="美剧"></i-tab>
      <i-tab key="6" title="动画"></i-tab>
      <i-tab key="7" title="演讲"></i-tab>
    </i-tabs>
    <swiper @change='changeView' :current="currentIndex">
      <swiper-item v-for="item in tabs" :key="item">
        <view>{{item.title}}</view>
      </swiper-item>
  </swiper>
    <!-- <i-grid v-for="item in vedioUrl" :key="item">
          <view>
            <video :src="item.url" danmu-list="danmuList" enable-danmu danmu-btn controls style="height:130px;"></video>
          </view>
          <i-panel :title="item.remark">
      </i-panel>
    </i-grid> -->
  </div>
</template>

<script>
export default {
  data () {
    return {
      current: "0",
      current_scroll: "0",
      currentIndex:0,
      tabs:[
        {key:"tab1",title:"推荐"},
        {key:"tab2",title:"六级"},
        {key:"tab3",title:"精选"},
        {key:"tab4",title:"热门"},
        {key:"tab5",title:"电影"},
        {key:"tab6",title:"美剧"},
        {key:"tab7",title:"动画"},
        {key:"tab8",title:"演讲"}
      ],
      vedioUrl: [
        {url:"https://vdept.bdstatic.com/7746746432616d5a3932597a39336977/3445506477386a77/50c0158d2eee9ed276492fdc7ab990521fd9f800d8dd37d8300c3329410d474325539a4e9489e913ba002be7a86f8304.mp4?auth_key=1575430906-0-0-6e9323a32d5c82a162c575b78ee3a0f2",remark:"介绍1"},
        {url:"https://vdept.bdstatic.com/44643641376b765a36486a4b6e7a7544/465635686267576b/0ade6e0c63ecf8973cca91660ec033a180e37e44d6b29651e80fc73eed5d5ead279b32eaeea9a11dddea44cd70f45545.mp4?auth_key=1575438273-0-0-3daaacd76b3fd1a1fde8df33cbf9b009",remark:"介绍2"},
        {url:"https://vdept.bdstatic.com/70447a4446336c337047727545624d69/6d74564363485832/ae25f9509b4d91ec4328bc71a72cda8889f6c00a4e41834834226d750a322ee43432c3468826a466437498c9993a8987.mp4?auth_key=1575438406-0-0-da201f605976e294bc71f31ae27550c6",remark:"介绍3"},
        {url:"https://vdept.bdstatic.com/583145455a6874397a394b4c3841784d/434e4b5048446d51/81d32ea0540abb2b9a325d2b34ed4df233c900022664d17efa621ccab230783d25f7b0529f6e1298facea9bd651c07b3.mp4?auth_key=1575442896-0-0-3d00ea178cd230b759ef8fa2ffbce052",remark:"介绍4"},
        {url:"https://vdept.bdstatic.com/5a364e665a79524a45664c566879545a/6d726c5a53313838/a5f659cc87fe69423799529ef0fb2166a8c815d4c57f7dd4074c0aad6e17f623ad788e13fd7f3e9505c7dfe48f34288a.mp4?auth_key=1575443041-0-0-4d4d22d28d5130b98e5e6a2ae554b140",remark:"介绍5"},
        {url:"https://vdept.bdstatic.com/4d4236377169575851767a6a656e4552/3466564266746a6b/51da48362d03b3a7e0e73adf40adc1b87c0fd482481da90ecf703b46e5e04f7deb014915b1b45e4a4884f68a5db7f25f.mp4?auth_key=1575443167-0-0-af1cac7477959212ed7d905952ba9011",remark:"介绍6"}
      ]
    }
  },
  methods: {
    handleChangeScroll(type){
      console.log(type)
        this.current_scroll = type.mp.detail.key
      // let url='../list/main?type=' + type.mp.detail.key
      // mpvue.navigateTo({ url })
    },

    changeView(e){
      console.log(e)
      const that = this
      if(e.mp.detail.current === type.mp.detail.key){
        return false
      }else{
        this.currentIndex = e.mp.detail.current
      }
    },

    created () {
   }
}
}
</script>

<style scoped>
.section tc{
  height: 100px;
}
</style>
