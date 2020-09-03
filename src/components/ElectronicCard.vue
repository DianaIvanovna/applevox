<template>
  <section class="electronic-card">
    <h3 class="electronic-card__title">Электронная карта</h3>
    <section class="card-pages">
      <div class="card-page card-page_active">
        <div class="card-page__img-background">
          <img src="@/assets/images/info-patient.svg" alt="icon info patient"
          class="card-page__img">
        </div>
        <div class="card-page__content">
          <h4 class="card-page__title">Информация о пациенте</h4>
          <div class="card-page__info">
            <ul class="card-page__list">
              <li class="card-page__list-item">Ваши личные данные</li>
              <li class="card-page__list-item">Рекомендации врачей</li>
              <li class="card-page__list-item">История болезней</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="card-page">
        <div class="card-page__img-background">
          <img src="@/assets/images/analyzes.svg" alt="icon info patient"
          class="card-page__img">
        </div>
        <div class="card-page__content">
          <h4 class="card-page__title">Результаты анализов</h4>
          <div class="card-page__info">
            <p class="card-page__text">Вы можете узнать здесь результаты своих анализов</p>
          </div>
        </div>
      </div>
      <div class="card-page">
        <div class="card-page__img-background">
          <img src="@/assets/images/add-info.svg" alt="icon info patient"
          class="card-page__img">
        </div>
        <div class="card-page__content">
          <h4 class="card-page__title">Добавить  информацию</h4>
          <div class="card-page__info">
            <p class="card-page__text">Добавляйте в свою электронную медицинскую
              карту новые данные</p>
          </div>
        </div>
      </div>
      <div class="card-page">
        <div class="card-page__img-background">
          <img src="@/assets/images/history.svg" alt="icon info patient"
          class="card-page__img">
        </div>
        <div class="card-page__content">
          <h4 class="card-page__title">История приемов</h4>
          <div class="card-page__info">
            <p class="card-page__text">Вся информация о полученных услугах за
              все время хранится здесь</p>
          </div>
        </div>
      </div>
    </section>
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
$grey:#EBE7FF;
.electronic-card{
  width: 100%;
  margin-bottom: 40px;
}
.electronic-card__title{
  @include  Rubik;
  font-size: 16px;
  line-height: 19px;
  color: #000000;
  margin-left: 40px;
  width: 150px;
  margin-top: 35px;
  margin: 15px;
}
.card-pages{
  margin-left: 20px;
  margin-right: auto;
  display: grid;
  grid-template-columns: 540px 540px;
  grid-gap: 16px;
}
.card-page{
  border-radius: 5px;
  display: flex;
  border: 2px solid $grey;
  &.card-page_active{
    border: 2px solid $secondary-color;
    .card-page__img-background{
      background-color: $secondary-color;
    }
    .card-page__title{
      border-bottom: 2px solid $secondary-color;
    }
  }
  width: 540px;
  height: 183px;
}
.card-page__img-background{
  background-color: #FFFFFF;
  width: 133px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-page__title{
  @include  Rubik;
  font-size: 28px;
  line-height: 33px;
  color: #000000;

  width: 335px;
  padding-bottom: 10px;
  margin: 20px 0px 15px 36px;
  border-bottom: 2px solid $grey;
}
.card-page__text{
  @include  Rubik;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  margin-left: 36px;
  width: 320px;
}
.card-page__list-item{
  @include  Rubik;
  font-size: 16px;
  line-height: 24px;
  color: #000000;
  list-style-type: none;
  &:before {
    color: $secondary-color; /* Цвет маркера */
    content: "\2022";  /* юникод точки */
    padding-right: 10px; /* Расстояние от маркера до текста */
    padding-left: 36px;
  }
}
</style>
