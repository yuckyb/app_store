<template>
<div>
<div class="search-bar">
    <van-row gutter="5">
        <van-col span="3"><img :src="locationIcon" width="80%" class="location-icon" /></van-col>
        <van-col span="16">
          <input type="text" class="search-input"/>
        </van-col>
        <van-col span="5"><van-button size="mini">查找</van-button></van-col>
    </van-row>
</div>
<div class="swiper-area">
    <van-swipe :autoplay="1500">
        <van-swipe-item v-for="(banner,index) in bannerPicArray" :key="index">
            <img :src="banner.imageUrl" width="100%"/>
        </van-swipe-item>
    </van-swipe>
</div>
</div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'ShoppingMall',
  data () {
    return {
      locationIcon:'',
      bannerPicArray:[
                {imageUrl:'https://img13.360buyimg.com/cms/jfs/t1/1272/39/6620/248733/5ba361bcE7e8ea1a9/6e71a3193ee4f75f.jpg'},
                {imageUrl:'https://img12.360buyimg.com/cms/jfs/t1/5677/19/3410/296893/5b997572E0974586e/3aad9aaa241df8be.jpg'},
                {imageUrl:'https://img10.360buyimg.com/cms/jfs/t1/2701/3/6882/270491/5ba3d2a5E8e6d9f77/43086a19ae6b1e42.jpg'},
            ]
    }
  },
  created(){
        axios({
            url: 'https://www.easy-mock.com/mock/5ae2427800247c2aa1efe442/SmileVue/',
            method: 'get',
        })
        .then(response => {
            console.log(response)
        })
        .catch((error) => {     
        })
  }
}
</script>
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.search-bar{
      height: 2.2rem;
      background-color: #e5017d;
      line-height:2.2rem;
  }
  .search-input{
      width:100%;
      height: 1.3rem;
      border-top:0px;
      border-left:0px;
      border-right:0px;
      border-bottom: 1px solid 1px !important ;
      background-color: #e5017d;
      color:#fff;
  }
  .location-icon{
      padding-top: .2rem;
      padding-left: .3rem;
  }
  .swiper-area{
    margin: auto;
      width:20rem;
      clear:both;
  }
</style>
