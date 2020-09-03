<template>
  <header class="header">
    <h1 class="header__title">Мой профиль</h1>
    <section class="header__buttons">
      <img src="@/assets/images/search.svg" alt="search icon" class="header__icon">
      <img src="@/assets/images/bell.svg" alt="bell icon" class="header__icon">
      <img src="@/assets/images/eye.svg" alt="eye icon" class="header__icon">
      <div class="header__avatar-background">
        <img src="@/assets/images/avatar.jpg" alt="avatar" class="header__avatar">
      </div>
      <img src="@/assets/images/disclose.svg" alt="disclose icon" class="header__icon">
    </section>
  </header>
</template>
<style lang="scss" scoped>
$primary-color: #003B72;
$secondary-color: #50CAFF;
$button-color: #7761FF;
@mixin Rubik{
    font-family: Rubik;
    font-style: normal;
    font-weight: normal;
}
@mixin Rubik500{
    font-family: Rubik;
    font-style: normal;
    font-weight: 500;
}
@mixin Rubik300{
    font-family: Rubik;
    font-style: normal;
    font-weight: 300;
}
  .header{
    background-color: $secondary-color;
    display: flex;
    justify-content: space-between;
    box-sizing: border-box;
    padding: 0px 40px;
  }
  .header__avatar{
    box-sizing: border-box;
    border-radius: 50%;
    width: 45px;
    height: 45px;
    position: absolute;
    top: 1.5px;
    left: 1.5px;
    object-fit: cover;
  }
  .header__avatar-background{
    position: relative;
    border: 1px solid #FFFFFF;
    box-sizing: border-box;
    width: 50px;
    height: 50px;
    border-radius: 50px;
    margin-right: 9px;
  }
  .header__buttons{
    display: flex;
  }
  .header__title{
    @include Rubik;
    font-size: 28px;
    line-height: 33px;
    margin: 12px 0px 10px;
    color: #FFFFFF;
  }
  .header__icon{
    align-self: center;
    margin-right: 20px;
    &:last-of-type{
      margin-right: 0px;
    }
  }
</style>
