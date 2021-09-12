<template>
  <div class="card [ m-2 p-2 p-sm-4 overflow-hidden shadow ]">
    <div class="grid [ card-body ]">
      <div class="grid-a title [ mx-auto p-1 p-sm-0 ]">
        <div class="title--inner">ZAIKOプレミアム*特典</div>
      </div>
      <img
        src="../assets/premium_mobile_coins-cropped.gif"
        class="grid-b [ img-fluid align-self-center ]"
        alt="携帯からコインが出てくるアニメーション"
      />
      <ul class="grid-c feature-list [ list-unstyled ps-0 ps-sm-4 mt-sm-2 ]">
        <li>
          <span class="feature-list--emphasis">初月会費**</span>(¥600)<span
            class="feature-list--emphasis"
            >無料</span
          >！
        </li>
        <li>
          購入<span class="feature-list--emphasis">手数料</span>が毎回<span
            class="feature-list--emphasis"
            >¥0</span
          >！
        </li>
        <li>
          購入時の<span class="feature-list--emphasis">ポイント還元</span
          >率1％！
        </li>
        <li>
          <span class="feature-list--emphasis">¥100</span>相当のポイント<span
            class="feature-list--emphasis"
            >プレゼント**</span
          >！
        </li>
        <li>
          ZAIKO TV掲載コンテンツが<span class="feature-list--emphasis"
            >見放題</span
          >！
        </li>
        <li>
          会員限定<span class="feature-list--emphasis">割引</span>や<span
            class="feature-list--emphasis"
            >高画像</span
          >・<span class="feature-list--emphasis">高音質</span>視聴 など
        </li>
      </ul>
      <div class="grid-d">
        <a href="#" class="action-button [ btn btn-success ]">
          登録して、お得な特典を今すぐ利用
        </a>
        <ul class="fine-print [ list-unstyled text-md-end mt-4 mb-0 ]">
          <li>
            *ZAIKOプレミアム（月額600円/初月無料）への登録にはクレジットカードが必要です。
          </li>
          <li>
            **初月無料＆ポイントプレゼントの対象となるのは、初回の登録時のみです。
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PremiumComponent",
};
</script>

<style lang="scss" scoped>
$breakpoint-sm: "min-width: 576px";
$breakpoint-md: "min-width: 768px";

.grid {
  display: grid;
  grid-template-columns: 30% 1fr;
  grid-template-rows: max-content 1fr max-content;
  grid-column-gap: 32px;
  grid-row-gap: 16px;
  grid-template-areas:
    "title title"
    "image list"
    "footer footer";

  @media ($breakpoint-sm) {
    grid-template-columns: repeat(2, 40%) 1fr;
    grid-column-gap: 8px;
    grid-template-areas:
      "title title image"
      "list list image"
      "footer footer footer";
  }
}

.grid-a {
  grid-area: title;
}
.grid-b {
  grid-area: image;
}
.grid-c {
  grid-area: list;
}
.grid-d {
  grid-area: footer;
}

.card {
  @include borderPink;
}
.title {
  background-color: $color-main;
  min-height: 37px;
  width: min(300px, 85%);
  position: relative;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: clamp(1rem, -0.5rem + 8vw, 1.3rem); // 300px: 1rem, 360px: 1.3rem
  font-weight: 700;
  color: $color-text-light;

  &--inner {
    transform: translateY(1px); // optically align this font
  }

  $ribbon-end-width: 30px;
  $ribbon-end-height: 33px;
  $ribbon-horizontal-offset: -23px;
  $ribbon-vertical-offset: -7px;

  &::before,
  &::after {
    content: "";
    width: $ribbon-end-width;
    height: $ribbon-end-height;
    background-image: url("../assets/premium_ribbon-end.svg");
    background-size: contain;
    background-repeat: no-repeat;
    position: absolute;
    bottom: $ribbon-vertical-offset;
    @media (max-width: 275px) {
      display: none;
    }
  }

  &::before {
    left: $ribbon-horizontal-offset;
  }

  &::after {
    right: $ribbon-horizontal-offset;
    transform: scaleX(-1);
  }
}

.feature-list {
  font-size: 12px;

  @media ($breakpoint-sm) {
    display: grid;
    grid-template-rows: repeat(3, max-content);
    grid-auto-flow: column;
    grid-column-gap: 8px;

    & > li:nth-last-child(-n + 3) {
      margin-left: 16px;
    }
  }

  li {
    line-height: 1.1;
    @media ($breakpoint-sm) {
      line-height: 1.3;
    }
  }

  li::before {
    content: "\2022";
    color: $color-main;
    font-size: 1.9em;
    position: relative;
    top: 4px;
    width: 12px;
    margin-left: -15px;
    display: inline-block;
  }

  &--emphasis {
    font-size: 1.4em;
    font-weight: 700;
    color: $color-main;
    white-space: nowrap;
  }
}

.action-button {
  width: 100%;
  font-weight: 700;
  background-color: $color-accent-dark;

  @media ($breakpoint-sm) {
    padding: 10px 0;
  }
}

.fine-print {
  font-size: 14px;
  color: $color-text-gray;

  & > * + * {
    margin-top: 4px;
  }

  @media ($breakpoint-md) {
    margin-right: -24px;
  }
}
</style>
