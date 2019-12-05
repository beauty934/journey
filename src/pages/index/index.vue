<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
    >
      <block v-for="img in imgUrls" :key="img">
        <swiper-item>
          <image :src="img" style="width:100%" />
        </swiper-item>
      </block>
    </swiper>
    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
 
</i-grid>
<i-panel :title="title_name">
    <view style="padding: 15px;">
      <i-card v-for="item in top" :key="item" i-class="split"  :extra="item.name" :thumb="item.image">
         <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
      </i-card>
       
    </view>
</i-panel>
  </div>
</template>

<script>

export default {
  data () {
    return {
     title_name:"热门",
     grids:[
       {title:"美食",image:"/static/images/1.png"},
       {title:"景区",image:"/static/images/2.png"},
       {title:"游乐",image:"/static/images/3.png"},
       {title:"高校",image:"/static/images/4.png"}
     ],
     top:[
       {name:"黄鹤楼",address:"地址：武汉市武昌区蛇山西山坡特1号",image:"/static/images/黄鹤楼.jpg",remark:"黄鹤楼位于武昌蛇山之巅，濒临万里长江，是国家5A级旅游景区，“江南三大名楼”之一，自古享有“天下江山第一楼“和”天下绝景“之称。黄鹤楼是武汉市标志性建筑，与晴川阁、古琴台并称“武汉三大名胜”。"},
       {name:"户部巷",address:"地址：湖北省武汉市解放路457附3号",image:"/static/images/户部巷.jpg",remark:"户部巷是一条长150米的百年老巷，被誉为“汉味小吃第一巷”，其繁华的早点摊群数十年经久不衰。"},
       {name:"湖北省博物馆",address:"地址：武汉市武昌区东湖路160号",image:"/static/images/湖北省博物馆.jpg",remark:"湖北省博物馆现有馆藏文物26万余件(套)，以青铜器、漆木器、简牍最有特色，其中国家一级文物945件(套)、国宝级文物16件(套)。越王勾践剑、曾侯乙编钟、郧县人头骨化石、元青花四爱图梅瓶为该馆四大镇馆之宝。要想了解湖北省的历史，湖北省博物馆绝对是第一选择！"},
       {name:"武汉大学",address:"地址：",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍4"}
     ],
      imgUrls: [
        '/static/images/WH1.jpg',
        '/static/images/WH2.jpg',
        '/static/images/WH3.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      circular: true,
      interval: 4000,
      duration: 1500
      }
  },
  methods: {
    goType(type){
     console.log(type)
     let url = '../list/main?type=' + type.title
     mpvue.navigateTo({ url })
    }
    },

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
margin-bottom: 10pt;
}
</style>