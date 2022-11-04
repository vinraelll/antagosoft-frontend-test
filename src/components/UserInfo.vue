<template>
  <div class="about">
    <div class="about__photo">
      <img src="@/assets/user-avatar.png" alt="user avatar" />
    </div>

    <div class="about__name">Eva Jonson</div>
    <div class="about__position">Sales Manager</div>
    <div class="about__slogan">
      <div class="about__slogan-inner">
        I will find the best offers for you. My services are absolutely free.
      </div>
    </div>
  </div>

  <div class="services">
    <div class="services__name">Services</div>

    <ul class="services__stats">
      <li class="services__stats-a">
        <span class="services__stats-text">Manual tour booking</span>
        <span class="services__stats-count">11</span>
      </li>
      <li class="services__stats-b">
        <span class="services__stats-text">Package tours</span>
        <span class="services__stats-count">3</span>
      </li>
      <li class="services__stats-c">
        <span class="services__stats-text">Hotels</span>
        <span class="services__stats-count">1</span>
      </li>
    </ul>

    <div class="services__total">
      <div class="services__total-text">Total</div>
      <span class="services__total-count">15</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserInfo",
};
</script>

<style lang="scss" scoped>
@import "@/scss/mixins.scss";
.about {
  position: relative;
  padding-top: 10px;
  padding-left: 90px;
  margin-bottom: 15px;

  &__photo {
    position: absolute;
    left: 0;
    width: 124px;
    height: 124px;

    & img {
      object-fit: cover;
      border-radius: 50%;
    }
  }

  &__name {
    margin-bottom: 2px;
    padding-top: 5px;
    font-size: 16px;
    font-weight: 700;
    padding-left: 45px;
  }

  &__position {
    margin-bottom: 5px;
    padding-left: 45px;
    font-size: 12px;
    color: #808080;
  }

  &__slogan {
    padding: 6px 10px 8px 45px;
    background-color: #fffbc8;
    border-radius: 5px;
    border: 1px solid #dadada;
  }
}

.services {
  padding-left: 135px;
  margin-bottom: 10px;
  font-size: 13px;

  @include phone-below {
    padding-left: 0;
  }

  &__name {
    padding-right: 24px;
    margin-bottom: 8px;
    text-align: right;
    line-height: 1.1;
  }

  &__stats {
    position: relative;
    padding: 16px 40px 16px 0;
    line-height: 2;
    border-top: 1px solid #dadada;
    border-bottom: 1px solid #dadada;

    @include phone-below {
      padding: 16px 20px 16px 0;
    }

    &::before {
      content: "";
      position: absolute;
      left: 0;
      width: 1px;
      height: 76px;
      background-color: #dadada;
      z-index: 2;
    }

    & li {
      padding-left: 6px;
    }

    &-count {
      font-weight: 700;
    }

    &-text,
    &-count {
      z-index: 2;
    }
  }

  &__stats-a,
  &__stats-b,
  &__stats-c,
  &__total {
    position: relative;
    display: flex;
    justify-content: space-between;
  }

  &__stats-a::before,
  &__stats-b::before,
  &__stats-c::before {
    content: "";
    position: absolute;
    left: 0;
    height: 24px;
    border-radius: 0px 3px 3px 0px;
    z-index: 1;
  }

  &__stats-a::before {
    width: 74%;
    background-color: #b1e19b;
  }

  &__stats-b::before {
    width: 18%;
    background-color: #ace2f8;
  }

  &__stats-c::before {
    width: 12%;
    background-color: #ace2f8;
  }

  &__total {
    padding-right: 40px;
    font-size: 16px;
    font-weight: 700;
    line-height: 1.6;

    @include phone-below {
      padding-right: 20px;
    }
  }
}
</style>
