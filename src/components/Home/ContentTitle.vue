<template>
  <div class="contentTitle">
    <div class="image">
      <img class="taobao_img" src="https://gw.alicdn.com/imgextra/i1/O1CN01LfyvED1TpRW5ppmks_!!6000000002431-2-tps-214-134.png" alt="">
      <a class="wenzi" href="www.baidu.com" >
        中国大陆
      </a>
    </div>
    <div class="title_search">
      <i class="iconfont icon-sousuo sousuo"></i>
      <input v-model="keyword" class="title_seacrh_input"  type="search" placeholder="搜索商品" >
      <!-- <el-button class="title_searcch_button" round>搜索</el-button> -->
      <div class="search_content" ref="search" v-show="keyword">
        <ul v-for="(item,index) in this.list" :key="index" @click="handleToProduct(item.id)">
          <li class="search-item border-bottom">{{item.car_name}}</li>
        </ul>
        <ul v-show="hasNoData">
          <li class="search-item border-bottom" >没有匹配的数据</li>
        </ul>
      </div>
      <div class="title_seacrh_wenzi">
        <a class="title_wenzi">海澜之家  套装 秋 移动电源 紧身裤牛仔高腰 洗衣机 泰茶 收纳盒   更多。。。</a>
      </div>
    </div>
    <button @click="clickme()">今日签到</button>
  </div>
</template>

<script>
export default {
  name:"ContentTitle",
  data(){
    return{
      keyword:"",
      hasNoData:"",
      timer:null,
      list:[],
      search: [
        {
          id: 1,
          car_name: "保时捷718",
          car_price: 98.6,
          howManyToBuy: 7,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c23/253110912_1612841700687_270x202.jpg",
          car_image2:"https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2101/05/c10/248575544_1609815682192_400x300.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
          car_color:["黑色","红色","黄色"],
          car_model:["顶配","中配","低配"],
          car_purchase_method:["全款"],
          car_package:["套餐一"]
        },
        {
          id: 2,
          car_name: "福特Mustang",
          car_price: 40.18,
          howManyToBuy: 9,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2106/11/c38/267921434_1623398664242_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 3,
          car_name: "保时捷911",
          car_price:  311.45,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/18/c8/253922922_1613650093274_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 4,
          car_name: "Aventador",
          car_price: 920.4733,
          howManyToBuy: 16,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/08/c11/252995866_1612760863848_270x202.png",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 5,
          car_name: "AMG GT",
          car_price: 368.88,
          howManyToBuy: 23,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/01/c6/252150543_1612171274847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 6,
          car_name: "奧迪 R8",
          car_price: 228.88,
          howManyToBuy: 1,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2104/25/c8/262576026_1619321507847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 7,
          car_name: "法拉利488",
          car_price: 449.9,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c29/253144346_1612860966069_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 8,
          car_name: "Huracán",
          car_price: 390.00,
          howManyToBuy: 8,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/07/c13/252873549_1612680347699_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 9,
          car_name: "魅影",
          car_price: 590.00,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255261791_1614560034303_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 1,
          car_name: "保时捷718",
          car_price: 98.6,
          howManyToBuy: 7,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c23/253110912_1612841700687_270x202.jpg",
          car_image2:"https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2101/05/c10/248575544_1609815682192_400x300.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 2,
          car_name: "福特Mustang",
          car_price: 40.18,
          howManyToBuy: 9,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2106/11/c38/267921434_1623398664242_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 3,
          car_name: "保时捷911",
          car_price:  311.45,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/18/c8/253922922_1613650093274_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 4,
          car_name: "Aventador",
          car_price: 920.4733,
          howManyToBuy: 16,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/08/c11/252995866_1612760863848_270x202.png",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 5,
          car_name: "AMG GT",
          car_price: 368.88,
          howManyToBuy: 23,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/01/c6/252150543_1612171274847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 6,
          car_name: "奧迪 R8",
          car_price: 228.88,
          howManyToBuy: 1,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2104/25/c8/262576026_1619321507847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 7,
          car_name: "法拉利488",
          car_price: 449.9,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c29/253144346_1612860966069_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 8,
          car_name: "Huracán",
          car_price: 390.00,
          howManyToBuy: 8,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/07/c13/252873549_1612680347699_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 9,
          car_name: "魅影",
          car_price: 590.00,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255261791_1614560034303_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 1,
          car_name: "保时捷718",
          car_price: 98.6,
          howManyToBuy: 7,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c23/253110912_1612841700687_270x202.jpg",
          car_image2:"https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2101/05/c10/248575544_1609815682192_400x300.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
          car_color:["黑色","红色","黄色"],
          car_model:["顶配","中配","低配"],
          car_purchase_method:["全款"],
          car_package:["套餐一"]
        },
        {
          id: 2,
          car_name: "福特Mustang",
          car_price: 40.18,
          howManyToBuy: 9,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2106/11/c38/267921434_1623398664242_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 3,
          car_name: "保时捷911",
          car_price:  311.45,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/18/c8/253922922_1613650093274_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 4,
          car_name: "Aventador",
          car_price: 920.4733,
          howManyToBuy: 16,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/08/c11/252995866_1612760863848_270x202.png",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 5,
          car_name: "AMG GT",
          car_price: 368.88,
          howManyToBuy: 23,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/01/c6/252150543_1612171274847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 6,
          car_name: "奧迪 R8",
          car_price: 228.88,
          howManyToBuy: 1,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2104/25/c8/262576026_1619321507847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 7,
          car_name: "法拉利488",
          car_price: 449.9,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c29/253144346_1612860966069_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 8,
          car_name: "Huracán",
          car_price: 390.00,
          howManyToBuy: 8,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/07/c13/252873549_1612680347699_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 9,
          car_name: "魅影",
          car_price: 590.00,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255261791_1614560034303_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 1,
          car_name: "保时捷718",
          car_price: 98.6,
          howManyToBuy: 7,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c23/253110912_1612841700687_270x202.jpg",
          car_image2:"https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2101/05/c10/248575544_1609815682192_400x300.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 2,
          car_name: "福特Mustang",
          car_price: 40.18,
          howManyToBuy: 9,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2106/11/c38/267921434_1623398664242_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 3,
          car_name: "保时捷911",
          car_price:  311.45,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/18/c8/253922922_1613650093274_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 4,
          car_name: "Aventador",
          car_price: 920.4733,
          howManyToBuy: 16,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/08/c11/252995866_1612760863848_270x202.png",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 5,
          car_name: "AMG GT",
          car_price: 368.88,
          howManyToBuy: 23,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/01/c6/252150543_1612171274847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 6,
          car_name: "奧迪 R8",
          car_price: 228.88,
          howManyToBuy: 1,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2104/25/c8/262576026_1619321507847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 7,
          car_name: "法拉利488",
          car_price: 449.9,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c29/253144346_1612860966069_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 8,
          car_name: "Huracán",
          car_price: 390.00,
          howManyToBuy: 8,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/07/c13/252873549_1612680347699_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 9,
          car_name: "魅影",
          car_price: 590.00,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255261791_1614560034303_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 1,
          car_name: "保时捷718",
          car_price: 98.6,
          howManyToBuy: 7,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c23/253110912_1612841700687_270x202.jpg",
          car_image2:"https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2101/05/c10/248575544_1609815682192_400x300.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
          car_color:["黑色","红色","黄色"],
          car_model:["顶配","中配","低配"],
          car_purchase_method:["全款"],
          car_package:["套餐一"]
        },
        {
          id: 2,
          car_name: "福特Mustang",
          car_price: 40.18,
          howManyToBuy: 9,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2106/11/c38/267921434_1623398664242_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 3,
          car_name: "保时捷911",
          car_price:  311.45,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/18/c8/253922922_1613650093274_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 4,
          car_name: "Aventador",
          car_price: 920.4733,
          howManyToBuy: 16,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/08/c11/252995866_1612760863848_270x202.png",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 5,
          car_name: "AMG GT",
          car_price: 368.88,
          howManyToBuy: 23,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/01/c6/252150543_1612171274847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 6,
          car_name: "奧迪 R8",
          car_price: 228.88,
          howManyToBuy: 1,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2104/25/c8/262576026_1619321507847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 7,
          car_name: "法拉利488",
          car_price: 449.9,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c29/253144346_1612860966069_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 8,
          car_name: "Huracán",
          car_price: 390.00,
          howManyToBuy: 8,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/07/c13/252873549_1612680347699_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 9,
          car_name: "魅影",
          car_price: 590.00,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255261791_1614560034303_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 1,
          car_name: "保时捷718",
          car_price: 98.6,
          howManyToBuy: 7,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c23/253110912_1612841700687_270x202.jpg",
          car_image2:"https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2101/05/c10/248575544_1609815682192_400x300.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 2,
          car_name: "福特Mustang",
          car_price: 40.18,
          howManyToBuy: 9,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2106/11/c38/267921434_1623398664242_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 3,
          car_name: "保时捷911",
          car_price:  311.45,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/18/c8/253922922_1613650093274_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },
        {
          id: 4,
          car_name: "Aventador",
          car_price: 920.4733,
          howManyToBuy: 16,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/08/c11/252995866_1612760863848_270x202.png",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 5,
          car_name: "AMG GT",
          car_price: 368.88,
          howManyToBuy: 23,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/01/c6/252150543_1612171274847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 6,
          car_name: "奧迪 R8",
          car_price: 228.88,
          howManyToBuy: 1,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2104/25/c8/262576026_1619321507847_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 7,
          car_name: "法拉利488",
          car_price: 449.9,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/09/c29/253144346_1612860966069_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 8,
          car_name: "Huracán",
          car_price: 390.00,
          howManyToBuy: 8,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2102/07/c13/252873549_1612680347699_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 9,
          car_name: "魅影",
          car_price: 590.00,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255261791_1614560034303_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
        {
          id: 10,
          car_name: "迈凯伦720S",
          car_price: 378.8,
          howManyToBuy: 5,
          car_image:
            "https://img.pcauto.com.cn/images/upload/upc/tx/auto5/2103/01/c2/255260091_1614559902341_270x202.jpg",
          introduce: "外形拉风，低矮跑车，一看就很有范，保时捷大家都认识",
        },       
      ],
    }
  },
  methods:{
    clickme(){
      this.$store.commit("addyouMoney",100);
    },
    handleToProduct(id){
      let router2 = this.list.filter(item => item.id === id)[0]
      this.$router.push({name:"itemList",
        params:{
            id:router2.id,
            car_name:router2.car_name,
            car_model:router2.car_model,
            car_price:router2.car_price,
            car_color:router2.car_color,
            car_image:router2.car_image,
            car_image2:router2.car_image2,
            introduce:router2.introduce,
            howManyToBuy:router2.howManyToBuy,
            car_purchase_method:router2.car_purchase_method,
            car_package:router2.car_package
          }
      })
    }
  },
  watch:{
    keyword(){
      if(this.timer){
        clearTimeout(this.timer)
      }
      if(!this.keyword){
        this.list = []
        return
      }
      this.timer = setTimeout(()=>{
        const result = []
        for(let i = 0;i < this.search.length;i++){

            if(this.search[i].car_name.indexOf(this.keyword) > -1){
              // console.log(this.search[i].product_name);
              result.push(this.search[i])
            }
        }
        if(result.length === 0){
          this.hasNoData = "社么都没用"
        }else{
          this.list = result
          this.hasNoData = ""
        }
      },100)
    }
  },
}
</script>

<style scoped>
  .contentTitle{
    display: flex;
    flex-flow: wrap;
    justify-content: space-evenly;
  }
  .image{
    height: 60px;
    /* width: 190px; */
    margin-top: 30px;
    display: flex;
    flex-direction: row;
    flex: 2;
    justify-content: flex-end;
  }
  .image > .taobao_img{
    height: 100%;
    width: 100px;
    padding-right: 10px;
    border-right: 2px solid orangered;
  }
  .image > .wenzi {
    height: 100%;
    width: 70px;
    font-size: 25px;
    margin-left: 10px;
    margin-top: -5px;
    color: orangered;
    text-decoration: none;
  }
  .title_search{
    margin-top: 20px;
    flex: 4;
    margin-left: 40px;
  }
  .title_seacrh_input{
    height: 50px;
    width: 630px;
    border-radius: 25px;
    border: 0px;
    outline:none;
    padding-left: 35px;
    /* flex: 6; */
  }
  input::-webkit-search-cancel-button{
    display: none;
  }
  input[type=search]::-ms-clear{
    display: none;
  }
  .iconfont{
    position: relative;
    /* color: #fff; */
    /* font-size: 15px; */
    left: 30px;
  }
  .title_seacrh_wenzi{
    margin-top: 10px;
  }
  .title_wenzi{
    font-size: small;
    color:	#A0A0A0;
    cursor: pointer;
    margin-left: 15px;
  }
  .title_wenzi:hover{
    color: orangered;
  }
  .search_content{
    width: 630px;
    /* height: 100%; */
    position: absolute;
    background-color: #fff;
    border-top-left-radius: 25px;
    border-top-right-radius: 25px;
    max-height: 500px;
    overflow: auto;
    z-index: 999;
    padding-top: 20px;
    margin-left: 17px;
  }
  .search_content > ul{
    height: 50px;
    width: 100%;
    /* border: 1px solid #000; */
    line-height: 50px;
  }
  .search_content > ul:hover{
    background-color: #f0f0f0;
    cursor: pointer;
  }
  .search_content > ul > li{
    margin-left: 20px;
  }
</style>