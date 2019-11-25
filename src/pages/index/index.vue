<template>
  <div>
    <div class="buttonBox">
      <div class="leftBox">
        <div class="imgScreen"><img src="/static/tabs/filter.png"></div>
        <!-- <div class="imgScreen" id="imgScreen"></div> -->
          <ul class="listBox">
          <li><button>推荐</button></li>
          <li><button>六级</button></li>
          <li><button>精选</button></li>
          <li><button>热门</button></li>
          <li><button>电影</button></li>
          <li><button>美剧</button></li>
          <li><button>动画</button></li>
          <li><button>演讲</button></li>
        </ul>
      </div>
      <div class="rightBox">
        <img src="/static/tabs/search.png">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  methods: {
  },

  created () {
  }
}
</script>

<style scoped>
.buttonBox{
  position:relative;
  width: 380px;
  height:30px;
  background-color:red;
}

.leftBox{
  width:88%;
  height:30px;
  line-height:200px;
  border: green solid 1px;
}

.imgScreen{
  float:left;
  margin-right: 5px;
  width:25px;
  height:25px;
}

.listBox{
  margin-left: 10px;
}

li{
  float: left;
}

button{
  font-size: 12px;
  background-color: Transparent; 
  border-style: none;    
  outline: none;     
}

.rightBox{
  width:12%;
  height:30px;
}

 img{
  width: 25px;
  height: 25px;
}

</style>
