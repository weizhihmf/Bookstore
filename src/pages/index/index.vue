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
          {url:"https://vdept.bdstatic.com/446c6a41657868777a53374952573274/5351345a62684a31/1000d2121a59602d56383fd5600b4eac4a72edb49a5f0ab272afe44e1765e232d32dadd1e2a4ff4ac3db27d30f63a793.mp4?auth_key=1576243517-0-0-eb0d514a743d45acd848ccc678321aa4",remark:"旋律好听"},
          {url:"https://vdept.bdstatic.com/4e77734252326978464631726a476e6a/4c65583531756670/6ba33b52478229659b9472078c9148757d3cc386ce229ad7fcc8477e2cd960359812c3cdbd422a5597c8ad8119a92d99.mp4?auth_key=1576243803-0-0-3ddf7af1f4c22cd8754473d182df9306",remark:"声音好听"},
          {url:"https://vdept.bdstatic.com/3136645744545a673564695938555946/6b556c784d657550/e22a970e3add790f6daa22e3cdff85022e295d43b574ef880e12172aa1c8b425eb21b006198a0a5b7745aa2e69c1e803.mp4?auth_key=1576243949-0-0-3bc05e5e4a9eb8b97754fe7230c94e07",remark:"介绍3"},
          {url:"https://vdept.bdstatic.com/57636a585a734e38574d3150396c5549/4e6665726a4c7054/30882e211875798c7e590c06551a48e7531cabbbb8e4d5a0af192ef4080d39a0cbf60d862451af154bf79fdc12ba4ea6.mp4?auth_key=1576244206-0-0-c64282c3f412e0123a0476beb4c9a37d",remark:"介绍4"},
          {url:"https://vdept.bdstatic.com/727947714a545267794873646c317976/42794e686e527348/caa69326acf6226a1b741356f0211707410c8591f08d81714c6b774d32d147b8630e6f75a40a2b0db268524fb4d95c86.mp4?auth_key=1576244425-0-0-b4a461e3c6a85229fb69f932ae59d960",remark:"介绍5"},
          {url:"https://vdept.bdstatic.com/4c586945444946513477493654395149/3942654c68554a78/8104942fc392fe20827359b6af25f56d5c2af0f82f6f5d5bf7fa7ffdf2f8e81e0005cc9d1fc4a0f18a11136043d3811e.mp4?auth_key=1576244608-0-0-c9224efbcbc9c222382ab776d193c655",remark:"介绍6"}
        ],
        [
          {url:"https://vdept.bdstatic.com/55345734737848784b6a784443494b6c/5257513642506363/57b86cdfafdcf4b6049041eb1dacfcd72d2ebb6f2497e33f69c7447fc1e26a72156401bcde915a145da51bd0b3d9c1b1.mp4?auth_key=1576244952-0-0-a81cf49d459ea12d07947eaa30dc650a",remark:"介绍1"}
        ],
        [
          {url:"https://vdept.bdstatic.com/4344646b6c5a355873764876474a4e69/5561594854577955/9848affa800cbd6a742534bc44de02e06e5a778c6d3ecc7ff880b16026d84fb921b79190724ba23395f670403ab0579f.mp4?auth_key=1576245130-0-0-93bafba18d1efa67abc97be395190a91",remark:"介绍1"}
        ],
        [
          {url:"https://vdept.bdstatic.com/4976324e4c68706e724c584353684e32/6b78376e394b3652/e708e6e5ff6f9844e5c6280e55e5f12ae1db16e49b885b82b0a9cea01703acc27e315ab62865a41b9864eab039f61c5e.mp4?auth_key=1576245543-0-0-d3ac17a0964eab43bf0fbbae3f2a57f5",remark:"介绍1"}
        ],
        [
          {url:"https://vdept.bdstatic.com/55533555423251333968335742334d71/6c77634575594b42/3913991edb3606c8022d50b1ba5afe44c591719b47965756a60f89ff4d65ab7adc06aaf998e2a4de421749aee9ec5b44.mp4?auth_key=1576245732-0-0-2329bd8f77bd4548d078e6b11c555738",remark:"介绍1"}
        ],
        [
          {url:"https://vdept.bdstatic.com/505151327464384459356c504c4e6954/6e324d746b323844/5c4c51479dcf5d28074f8daf95d40e2b831f318ba4bf11262ae324939d6dec934ffad3822e04ea187423bf03c70340cb.mp4?auth_key=1576245809-0-0-df4f069394412a934b7171c71dfa35bf",remark:"介绍1"}
        ],
        [
          {url:"https://vdeptold.bdstatic.com/4555394e335067324168677a4d37706d/6b5934333868747a/30b129585fb05bb1c601b51330066c9312f168946229141cac8f9f2436d549af9b9f9a3d0285ee9790774d019489c415.mp4?auth_key=1576245914-0-0-0d99001ae869af72b77bbc2e713b22aa",remark:"介绍1"}
        ],
        [
          {url:"https://vdept.bdstatic.com/4148547537537a346259506e65734c70/66446c5275493169/cd5c3386c1e023432596e49526050ee4e429ef4911066aa0da635c7aebeecb3f0cb5e08d2cfea3dc8275f9981cf26385.mp4?auth_key=1576246087-0-0-9650a1e18fcf8db742d381cb212dbfe8",remark:"介绍1"}
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
