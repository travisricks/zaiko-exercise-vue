<template>
  <div class="coupon card m-2 text-center">
    <div class="card-body">
      <div class="ribbon">クーポン</div>
      <div class="coupon__title mt-5 mt-sm-0">今回の割引金額*</div>
      <div class="coupon__amount">
        ￥<span class="coupon__amount--value">{{amount.toLocaleString()}}</span>割引
      </div>
      <div>
        <a href="#" class="btn btn-success">ZAIKOプレミアムに登録**して割引を受ける</a>
      </div>
      <div>
        <a href="#">今回は見送る</a>
      </div>
      <div>
        <ul>
          <li>
            *初月無料＆サインアップボーナスの対象となるのは、初回の登録時のみです。
          </li>
          <li>
            **ZAIKOプレミアム（月額600円/初月無料）への登録にはクレジットカードが必要です。
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CouponComponent',
  props: {
    amount: {
      type: Number,
      required: true,
      default: 0
    }
  }
}
</script>

<style lang="scss" scoped>
.card {
  overflow: hidden; // used for the top-right ribbon
}

.coupon {
  &__title {
    $spacing: 16px;

    // font-weight: 700;
    font-size: 24px;
    &::before {
      content: '\2044'; // using a fractional slash because the spacing is more symmetrical than a backslash in this font
      margin-right: $spacing;
      display: inline-block;
      transform: scaleX(-1);
    }
    &::after {
      content: '\2044';
      margin-left: $spacing;
    }
  }

  &__amount {
    background-image: url('../assets/coupon.png');
    background-size: auto 100%;
    background-repeat: no-repeat;
    background-position: center;
    height: 88px;

    display: flex;
    justify-content: center;
    align-items: baseline;

    font-size: 24px;
    font-weight: 700;
    line-height: 88px;
    color: $color-text-light;

    &--value {
      font-size: 1.75em;
      margin-left: 5px;
      margin-right: 5px;
    }
  }
}

.ribbon {
  width: 245px;
  height: 40px;
  position: absolute;
  top: 25px;
  right: -55px;
  transform: rotate(30deg);
  display: flex;
  justify-content: center;
  align-items: center;
  background: $color-main;
  color: $color-text-light;
  font-weight: 700;
  font-size: 20px;
  line-height: 1px;
  letter-spacing: 1px;
  user-select: none;
}
</style>
