<template>
  <div>
    <!-- <div class="buttonBox">
      <div class="leftBox">
        <div><img class="imgScreen" src="/static/tabs/filter.png"></div> -->
          <i-tabs :current="current_scroll" scroll @change="handleChangeScroll">
            <i-tab key="tab1" title="推荐"></i-tab>
            <i-tab key="tab2" title="六级"></i-tab>
            <i-tab key="tab3" title="精选"></i-tab>
            <i-tab key="tab4" title="热门"></i-tab>
            <i-tab key="tab5" title="电影"></i-tab>
            <i-tab key="tab6" title="美剧"></i-tab>
            <i-tab key="tab7" title="动画"></i-tab>
            <i-tab key="tab8" title="演讲"></i-tab>
          </i-tabs>
          <i-grid v-for="grid in grids" :key="grid">
            <i-grid-item>
              <i-grid-icon>
                <image :src="grid.image" />
              </i-grid-icon>
              <i-grid-label>{{grid.remark}}</i-grid-label>
            </i-grid-item>
          </i-grid>
      <!-- </div>
      <div class="rightBox">
        <img class="rightImg" src="/static/tabs/search.png">
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  data () {
    return {
      current: "tab1",
      current_scroll: "tab1",
      grids:[
        {remark:"介绍1", image:"/static/images/user.png"},
        {remark:"介绍2", image:"/static/images/user.png"},
        {remark:"介绍3", image:"/static/images/user.png"},
        {remark:"介绍4", image:"/static/images/user.png"},
        {remark:"介绍5", image:"/static/images/user.png"},
        {remark:"介绍6", image:"/static/images/user.png"}
      ]
    }
  },
  methods: {
    handleChangeScroll(e){
      console.log(e)
        this.current_scroll = e.mp.detail.key
    },

    created () {
   }
}
}
</script>

<style scoped>
.buttonBox{
  position:relative;
  width: 380px;
  height:30px;
}

.leftBox{
  float: left;
  width:88%;
  height:30px;
  line-height:200px;
}

.imgScreen{
  float:left;
  width: 25px;
  height: 25px;
}


.rightBox{
  float: left;
  width:10%;
  height:30px;
  line-height:200px;
}

.rightImg{
  float: right;
  width: 25px;
  height: 25px;
  margin-right: 5px;
}

</style>
