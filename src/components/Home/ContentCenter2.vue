<template>
  <div class="contentcenter">
    <div class="contentcenter_frame">
      <span class="contentcenter_frame_title">
        ifashion <span class="contentcenter_frame_title_span">時尚穿搭</span>
      </span>
      <div class="contentcenter_frame_image">
        <div class="contentcenter_frame_image_big">
          <img src="https://gw.alicdn.com/imgextra/i1/750350118/O1CN01x0KvRq1Ck5QiWJ3rL_!!0-item_pic.jpg_240x10000Q75.jpg" alt="" />
        </div>
        <div class="contentcenter_frame_image_small">
          <div class="contentcenter_frame_image_small_1">
            <img src="https://gw.alicdn.com/imgextra/i1/2208218977743/O1CN01gE3apT274LLTnNXOg_!!2208218977743.jpg_140x10000Q75.jpg" alt="" />
            <img src="https://gw.alicdn.com/imgextra/i1/695892340/O1CN01kSVWDo1T9lVb0LepW_!!695892340-0-picasso.jpg_140x10000Q75.jpg" alt="" />
          </div>
        </div>
      </div>
      <div class="contentcenter_frame_com">
        <div class="contentcenter_frame_com_image">
          <img src="../../assets/img/login_image1.png" alt="" />
        </div>
        <div class="contentcenter_frame_com_wenzi">
          <div class="contentcenter_frame_com_wenzi_title">达人推荐</div>
          <div class="contentcenter_frame_com_wenzi_content">
            <img
              src="../../assets/img/login_image1.png"
              alt=""
            />年轻人的潮流推荐
          </div>
        </div>
        <div class="contentcenter_frame_com_symbol">
            <div>
                >
            </div>
        </div>
      </div>
    </div>
    <div class="contentcenter_frame">
      <span class="contentcenter_frame_title">
        ifashion <span class="contentcenter_frame_title_span">時尚穿搭</span>
      </span>
      <div class="contentcenter_frame_image">
        <div class="contentcenter_frame_image_big">
          <img src="https://gw.alicdn.com/imgextra/i3/215085429/O1CN01WW1sOw1pyWujLmtiv_!!215085429.jpg_240x10000Q75.jpg" alt="" />
        </div>
        <div class="contentcenter_frame_image_small">
          <div class="contentcenter_frame_image_small_1">
            <img src="https://gw.alicdn.com/imgextra/i2/2038226538/O1CN01CFaX1B1yAS9cczqgt_!!0-item_pic.jpg_140x10000Q75.jpg" alt="" />
            <img src="https://gw.alicdn.com/imgextra/i4/3179335342/O1CN017BbuBF1pKgOEHGf01_!!0-item_pic.jpg_140x10000Q75.jpg" alt="" />
          </div>
        </div>
      </div>
      <div class="contentcenter_frame_com">
        <div class="contentcenter_frame_com_image">
          <img src="../../assets/img/login_image1.png" alt="" />
        </div>
        <div class="contentcenter_frame_com_wenzi">
          <div class="contentcenter_frame_com_wenzi_title">达人推荐</div>
          <div class="contentcenter_frame_com_wenzi_content">
            <img
              src="../../assets/img/login_image1.png"
              alt=""
            />年轻人的潮流推荐
          </div>
        </div>
        <div class="contentcenter_frame_com_symbol">
            <div>
                >
            </div>
        </div>
      </div>
    </div>
    <div class="contentcenter_frame">
      <span class="contentcenter_frame_title">
        ifashion <span class="contentcenter_frame_title_span">時尚穿搭</span>
      </span>
      <div class="contentcenter_frame_image">
        <div class="contentcenter_frame_image_big">
          <img src="https://gw.alicdn.com/imgextra/i4/2845299902/O1CN01nsL9jB2N1AVxjGcAx_!!2845299902.jpg_240x10000Q75.jpg" alt="" />
        </div>
        <div class="contentcenter_frame_image_small">
          <div class="contentcenter_frame_image_small_1">
            <img src="https://gw.alicdn.com/imgextra/i3/2834938110/TB25LFMX0hvOuFjSZFBXXcZgFXa_!!2834938110.jpg_140x10000Q75.jpg" alt="" />
            <img src="https://gw.alicdn.com/imgextra/i1/80978148/O1CN01YIyEbc2A3piaJpy0F_!!80978148.jpg_140x10000Q75.jpg" alt="" />
          </div>
        </div>
      </div>
      <div class="contentcenter_frame_com">
        <div class="contentcenter_frame_com_image">
          <img src="../../assets/img/login_image1.png" alt="" />
        </div>
        <div class="contentcenter_frame_com_wenzi">
          <div class="contentcenter_frame_com_wenzi_title">达人推荐</div>
          <div class="contentcenter_frame_com_wenzi_content">
            <img
              src="../../assets/img/login_image1.png"
              alt=""
            />年轻人的潮流推荐
          </div>
        </div>
        <div class="contentcenter_frame_com_symbol">
            <div>
                >
            </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "ContentCenter2",
  data() {
    return {};
  },
};
</script>

<style scoped>
.contentcenter {
  position: relative;
  width: 1200px;
  height: 400px;
  background-color: #fff;
  left: 50%;
  transform: translate(-50%);
  display: flex;
  justify-content: space-around;
  border-radius: 12px;
  margin-top: 20px;
}
.contentcenter_frame {
  width: 355px;
  height: 100%;
  float: left;
}
.contentcenter_frame_title {
  height: 80px;
  width: 100%;
  font-size: 25px;
  line-height: 80px;
  margin-left: 20px;
}
.contentcenter_frame_title_span {
  padding: 0 5px;
  font-size: 15px;
  background-color: cornflowerblue;
  color: #fff;
  border-radius: 3px;
}
.contentcenter_frame_image {
  width: 100%;
  height: 235px;
  /* background-color: crimson; */
  display: flex;
  justify-content: space-between;
}
.contentcenter_frame_image_big {
  width: 235px;
  height: 100%;
}
.contentcenter_frame_image_big > img {
  width: 100%;
  height: 100%;
  border-radius: 12px;
}
.contentcenter_frame_image_small {
  width: 115px;
  height: 100%;
}
.contentcenter_frame_image_small_1 {
  width: 100%;
  height: 115px;
}
.contentcenter_frame_image_small_1 > img {
  width: 100%;
  height: 100%;
  border-radius: 12px;
}
.contentcenter_frame_com {
  margin-top: 16px;
  width: 100%;
  height: 53px;
  display: flex;
}
.contentcenter_frame_com_image {
  flex: 2;
  width: 40px;
  height: 100%;
}
.contentcenter_frame_com_image > img {
  width: 46px;
  height: 46px;
  position: relative;
  top: 50%;
  left: 0;
  transform: translate(0, -50%);
}
.contentcenter_frame_com_wenzi {
  flex: 7;
  width: 40px;
  height: 100%;
}
.contentcenter_frame_com_wenzi_title {
  font-size: 17px;
}
.contentcenter_frame_com_wenzi_content > img {
  margin-right: 10px;
  width: 16px;
  height: 16px;
  position: relative;
  top: 3px;
}
.contentcenter_frame_com_wenzi_content {
  color: slateblue;
  font-size: 13px;
  line-height: 35px;
}
.contentcenter_frame_com_symbol {
  flex: 1;
  width: 40px;
  height: 100%;
  line-height: 46px;
  text-align: center;
}
.contentcenter_frame_com_symbol > div{
    color: slateblue;
    font-size: 40px;
}
</style>