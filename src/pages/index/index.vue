<template>
  <div @click="clickHandle">

    <div class="buttonBox" @click="bindViewTap">
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

    <div class="usermotto">
      <div class="user-motto">
        <card :text="motto"></card>
      </div>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },

  components: {
    card
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
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

.leftBox img{
  width:25px;
  height:25px;
  /* display: inline-block; 
  vertical-align: middle; */
}

.imgScreen{
  float:left;
  margin-right: 5px;
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
