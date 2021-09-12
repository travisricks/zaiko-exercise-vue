<template>
  <div class="coupon [ card m-2 text-center ]">
    <div class="card-body flow">
      <div class="ribbon">クーポン</div>
      <div class="coupon__title [ mt-6 mt-sm-0 text-start text-sm-center ps-4 ps-sm-0 ]">今回の割引金額*</div>
      <div class="coupon__amount">
        <span>￥<span class="coupon__amount--value">{{amount.toLocaleString()}}</span>割引</span>
      </div>
      <div>
        <a href="#" class="coupon__button [ btn btn-success ]">ZAIKOプレミアムに登録**して割引を受ける</a>
      </div>
      <div class="coupon__text-link-wrapper">
        <a href="#" class="coupon__text-link">今回は見送る</a>
      </div>
      <div>
        <ul class="coupon__fine-print [ list-unstyled text-start text-sm-end mt-4 ]">
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
.flow > * + * {
  margin-top: 0.5rem;
}

.coupon {
  overflow: hidden; // used for the top-right ribbon
  border: 2px solid $color-main;
  border-radius: 10px;

  &__title {
    $spacing: 16px;
    font-size: 20px;
    font-weight: 500;
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
    background-image: url('../assets/coupon.svg');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    height: clamp(85px, 10vw, 110px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-right: 4%;
    font-size: 24px;
    font-size: clamp( 1rem, 6vw, 1.9rem );
    font-weight: 700;
    color: $color-text-light;

    &--value {
      font-size: 1.75em;
      margin-left: 5px;
      margin-right: 5px;
    }
  }

  &__button {
    width: min(90%, 500px);
    background-color: $color-accent-dark;
    font-weight: 700;
    border-color: transparent;
  }

  &__text-link {
    @include links($color-text-dark, $color-text-dark, $color-main, $color-main-dark);
  }

  &__fine-print {
    font-size: 14px;
    color: $color-text-gray;

    & > li + li {
      margin-top: .25rem;
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
  line-height: initial;
  letter-spacing: 1px;
  user-select: none;
}
</style>
