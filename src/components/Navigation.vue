<template>
  <section class="nav">
    <div class="">
      <h2 class="nav__title">Логотип</h2>
      <nav>
      <div class="nav__container-link nav__container-link_active">
        <img src="@/assets/images/heart.svg" alt="icon heart" class="nav__icon">
        <a href="#" class="nav__link">Профиль</a>
      </div>
      <div class="nav__container-link">
        <img src="@/assets/images/stethoscope.svg" alt="icon stethoscope" class="nav__icon">
        <a href="#" class="nav__link">Врачи и клиники</a>
      </div>
      <div class="nav__container-link">
        <img src="@/assets/images/Messages.svg" alt="icon Messages" class="nav__icon">
        <a href="#" class="nav__link">Сообщения</a>
      </div>
      <div class="nav__container-link">
        <img src="@/assets/images/test.svg" alt="icon test" class="nav__icon">
        <a href="#" class="nav__link">Тестирование</a>
      </div>
      <div class="nav__container-link">
        <img src="@/assets/images/book.svg" alt="icon book" class="nav__icon">
        <a href="#" class="nav__link">Полезно знать</a>
      </div>
    </nav>
    <button class="nav__button">Подать заявку</button>
    </div>
    <div>
      <div class="nav__container-link">
        <img src="@/assets/images/help.svg" alt="icon help" class="nav__icon">
        <a href="#" class="nav__link">Помощь</a>
      </div>
      <img src="@/assets/images/logo.svg" alt="logo" class="nav__logo">
    </div>
  </section>
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
.nav{
  background-color: $primary-color;
  height: 100vh;
  width: 190px;
  // padding: 20px;
  box-sizing: border-box;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  position:fixed;
  top:0px;
  left: 0px;
}
.nav__container-link{
  height: 55px;
  display: flex;
  align-items: center;
  &.nav__container-link_active{
    background-color: #fff;
    .nav__link{
      color: $button-color;
    }
  }
}

.nav__link{
  @include Rubik;
  font-size: 14px;
  line-height: 17px;
  text-decoration: none;
  color: #FFFFFF;
}
.nav__title{
  @include Rubik;
  font-size: 14px;
  line-height: 17px;
  color: #FFFFFF;
  height: 55px;
  box-sizing: border-box;
  margin: 0px;
  padding: 20px;
}
.nav__button{
  @include Rubik500;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  color: #FFFFFF;

  padding: 12px 24px 11px 25px;
  background-color: $button-color;
  border: none;
  border-radius: 5px;

  width: 150px;
  height: 40px;
  margin-top: 10px;
  margin-left: 20px;
}
.nav__icon{
  margin-right: 14px;
  padding-left: 20px;
}
.nav__logo{
  padding: 0px 20px 20px 20px;
}
</style>
