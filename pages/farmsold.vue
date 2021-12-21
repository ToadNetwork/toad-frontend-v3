<template>
  <v-row>
    <v-col cols="12" md="6" offset-md="3">
      <v-card
        style="padding-bottom:30px"
        elevation="8">
        <div data-animation="fadeInUp" data-animation-delay="0.6s" class="box_wrap radius_box bg-white text-center animation animated fadeInUp" style="margin-top: 60px;animation-delay: 0.6s;opacity: 1;">
          <h4 style="
              font-size: 30px;
              padding-top: 25px;
              font-weight: 500;
              letter-spacing: 2px;
              ">TOAD</h4>
          <img src="https://d33wubrfki0l68.cloudfront.net/4e5f36d85fde5cbd2921b558e4a36ba2d8a3278f/93d03/assets/images/logo.png" alt="wc_icon1" style="height: 70px;"> 
          <h4>
              <div id="rewards2" style="
                font-size: 33px;
                ">0.000</div>
              <span style="margin-top: 5px; display: block; font-size: 15px; font-weight: normal; color: rgb(185, 181, 180);">Toad Earned</span>
          </h4>
          <h5 style="/* margin-left: 200px; */padding: 0px 0px 15px;margin: 35px 15px 15px;border-bottom: 1px solid rgb(255 255 255 / 91%);font-size: 17px;font-weight: 500;color: rgb(255 255 255);display: block;text-align: left;"><img src="https://d33wubrfki0l68.cloudfront.net/ff18086b8502e05fc183e2b61e372d417f7c8f37/14001/assets/images/logo-small.png" alt="" style="
              line-height: 40px;
              vertical-align: text-bottom;
              ">
              TOAD Balance
              <span id="tokenBalance2" style="color: rgb(224 224 224);font-weight: bold;float: right;padding: 0px;line-height: 30px;">0.000</span>
          </h5>
          <h5 style="padding: 0px 0px 15px;margin: 0px 15px 15px;border-bottom: 1px solid rgb(240, 240, 240);font-size: 17px;font-weight: 500;color: rgb(255 255 255); display: block; text-align: left;"><img src="https://d33wubrfki0l68.cloudfront.net/ff18086b8502e05fc183e2b61e372d417f7c8f37/14001/assets/images/logo-small.png" alt="" style="
              vertical-align: text-bottom;
              ">
              Your Stake
              <span id="stakedBalance2" style="color: rgb(210 210 210);font-weight: bold;float: right;padding: 0px;line-height: 30px;">0.000</span>
          </h5>
          <h5 style="padding: 0px 0px 15px;margin: 0px 15px 15px;border-bottom: 1px solid rgb(240, 240, 240);font-size: 17px;font-weight: 500;color: rgb(234 234 234);display: block;text-align: left;"><img src="https://d33wubrfki0l68.cloudfront.net/ff18086b8502e05fc183e2b61e372d417f7c8f37/14001/assets/images/logo-small.png" alt="" style="
              vertical-align: text-bottom;
              ">
              Daily ROI
              <span id="roi2" style="color: rgb(241 241 241);font-weight: bold;float: right;padding: 0px;line-height: 30px;">0.000</span>
          </h5>
          <h5 style="padding: 0px 0px 15px;margin: 0px 15px 15px;border-bottom: 1px solid rgb(240, 240, 240);font-size: 17px;font-weight: 500;color: rgb(255 255 255);display: block;text-align: left;"><img src="https://d33wubrfki0l68.cloudfront.net/ff18086b8502e05fc183e2b61e372d417f7c8f37/14001/assets/images/logo-small.png" alt="" style="
              vertical-align: text-bottom;
              ">
              APY
              <span id="apy2" style="color: rgb(230 230 230);font-weight: bold;float: right;line-height: 30px;padding: 0px;">0.000</span>
          </h5>
          <div class="pool_stake_unstake" style="display: flex; align-items: center; margin-bottom: 20px; justify-content: space-between; padding-top: 16px;">
              <a id="approve_or_buy2" onclick="approve(2)" class="btn btn-default btn-radius animation animated fadeInUp" style="background: rgba(0, 0, 0, 0) linear-gradient(
                128.17deg
                , rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) repeat;font-weight: 500;letter-spacing: 1px;margin-left: 20px;text-transform: uppercase;font-size: 14px !important;height: 37px !important;border-radius: 12px;/* background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(87 85 243 / 32%) -14.78%, rgb(192 108 255 / 74%) 110.05%) repeat scroll 0% 0%; */font-size: 14px;height: 40px;line-height: 37px;padding: 0px 25px;/* margin-left: 0px; */margin-right: 10px;color: white;opacity: 1;">Approve</a> 
              <div style="align-items: flex-end; display: flex; flex-direction: column-reverse;"><input type="text" name="" id="tokenAmount2" class="form-control" style="border-radius: 15px;max-width: none;padding-right: 35px;height: 37px;margin: 0px;line-height: 37px;width: 13vw;"><span id="max2" onclick="maxAmount(2)" style="padding: 3px; cursor: pointer; background: rgb(77, 77, 241); margin-right: 5px; position: absolute; font-size: 10px; line-height: 10px; color: white; margin-bottom: 10px; border-radius: 6px;">max</span></div>
              <a id="approve_or_buy2" onclick="approve(2)" class="btn btn-default btn-radius animation animated fadeInUp" style="font-weight: 500;letter-spacing: 1px;margin-right: 20px !important;text-transform: uppercase;font-size: 14px !important;height: 37px !important;border-radius: 12px;background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) repeat scroll 0% 0%;font-size: 14px;height: 40px;line-height: 37px;padding: 0px 25px;/* margin-left: 10px; *//* margin-right: 10px; */color: white;opacity: 1;">Unstake
              </a>
          </div>
          <button id="approve_or_buy2" onclick="approve(2)" class="btn btn-default btn-radius animation animated fadeInUp" style="/* margin-left: 0px !important; */width: 93%;margin-left: 0% !important;/* line-height: 40px !important; */font-weight: 500;letter-spacing: 1px;margin-left: 20px;text-transform: uppercase;font-size: 14px !important;/* height: 40px; */border-radius: 12px;background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) repeat scroll 0% 0%;font-size: 14px;height: 37px;/* line-height: 21px; */padding: 10px 25px;/* margin-left: 0px; *//* margin-right: 10px; */color: white;/* min-width: 200px; */opacity: 1;">WITHDRAW</button><br> <button id="approve_or_buy2" onclick="approve(2)" class="btn btn-default btn-radius animation animated fadeInUp" style="margin-top: 15px;/* margin-left: 0px !important; */width: 93%;margin-left: 0% !important;/* line-height: 40px !important; */font-weight: 500;letter-spacing: 1px;margin-left: 20px;text-transform: uppercase;font-size: 14px !important;/* height: 40px; */border-radius: 12px;background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) repeat scroll 0% 0%;font-size: 14px;height: 37px;/* line-height: 21px; */padding: 10px 25px;/* margin-left: 0px; *//* margin-right: 10px; */color: white;/* min-width: 200px; */opacity: 1;">REINVEST</button> <button id="approve_or_buy2" onclick="approve(2)" class="btn btn-default btn-radius animation animated fadeInUp" style="margin-top: 15px;/* margin-left: 0px !important; */width: 93%;margin-left: 0% !important;/* line-height: 40px !important; */font-weight: 500;letter-spacing: 1px;margin-left: 20px;text-transform: uppercase;font-size: 14px !important;/* height: 40px; */border-radius: 12px;background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(228 0 255) -14.78%, rgb(220 200 56) 110.05%) repeat scroll 0% 0%;font-size: 14px;height: 37px;/* line-height: 21px; */padding: 10px 25px;/* margin-left: 0px; *//* margin-right: 10px; */color: white;/* min-width: 200px; */opacity: 1;">MORE INFO</button>
        </div>
      </v-card>
    </v-col>
    <v-col class="text-center">
    </v-col>
  </v-row>

</template>

<script>
export default {
  data () {
    return {
      loader: null,
      loading: false,
      loading2: false,
      loading3: false,
      loading4: false,
      loading5: false
    }
  },
  methods: {
  },
  watch: {
    loader () {
      const l = this.loader
      this[l] = !this[l]
      setTimeout(() => (this[l] = false), 3000)
      this.loader = null
    }
  }
}
</script>
