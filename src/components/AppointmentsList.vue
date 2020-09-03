<template>
  <section class ="appointments-list">
    <div class="appointment-container"
      v-bind:class="{ 'appointment-container_vertically':horizontallyAppointmets }">
      <div class="appointment"
        v-for = "card of appointmentsData"
        v-bind:key="card">
        <p class="appointment__date">{{card.date}}</p>
        <p class="appointment__adress">{{card.adress}}</p>
        <div class="appointment__info">
          <img :src="card.avatar" alt="photo doctor" class="appointment__img">
          <div class="doctor">
            <p class="doctor__name">{{card.doctorName}}</p>
            <p class="doctor__type">{{card.doctorType}}</p>
          </div>
          <button class="appointment__button">Отменить</button>
        </div>
      </div>
    </div>
    <p class="appointments-list__show-all"
        v-if="!horizontallyAppointmets">Еще {{appointmentsData.length - 2}} записи
      <button class="appointments-list__link" @click="showAll()">Подробнее</button>
    </p>
  </section>
</template>
<script>
import axios from 'axios';

export default {
  props: ['horizontallyAppointmets'],
  data() {
    return {
      appointmentsData: {
        appointments: [],
      },
      dates: [],
      flagShowAll: false,
    };
  },
  mounted() {
    axios
      .get('https://dianaivanovna.github.io/appvelox/appointments.json')
      .then((res) => {
        this.appointmentsData = res.data.appointments;
        this.dates = this.appointmentsData.map((item) => { // сделала отдельный массив для дат
          let date = item.date.match(/[0-9]{2}.[0-9]{2}.[0-9]{2}/);
          date = `20${date[0].slice(6, 8)}-${date[0].slice(3, 5)}-${date[0].slice(0, 2)}`;
          return date;
        });
      });
  },
  methods: {
    showAll() {
      this.flagShowAll = !this.flagShowAll;
      this.$emit('hidecard',
        {
          flag: true,
          dates: this.dates,
        });
    },
  },
};
</script>
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
.appointments-list{
  display: flex;
  align-items: center;
}
.appointments-list__show-all{
  @include Rubik;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  color: #000000;
  .appointments-list__link{
    color: $secondary-color;
    background-color: white;
    border: none;
    text-decoration: underline;
    padding: 0px;
  }
}
.appointment-container{
  display: flex;
  flex-wrap: nowrap;
  overflow: hidden;
  max-width: 1050px;
}
.appointment-container_vertically{
  flex-direction: column;
  height: 500px;
  overflow: auto;
  .appointment{
    margin-bottom: 15px;
  }
  &::-webkit-scrollbar-track { // поменяла цвет скролла
    background-color:#EBE7FF;
    -webkit-border-radius: 5px;
    border-radius: 5px;
  }
  &::-webkit-scrollbar-thumb { // цвет бегунка скролла
    -webkit-border-radius: 5px;
    background-color: $primary-color;
    border-radius: 5px;
  }
  &::-webkit-scrollbar{
    width: 8px;
  }
}
.appointment{
  box-sizing: border-box;
  border: 2px solid #EBE7FF;
  border-radius: 5px;
  margin-left: 20px;
  padding: 20px;
  min-width: 475px;
  position: relative;
}
.appointment__date{
  @include Rubik500;
  font-weight:bold;
  font-size: 16px;
  line-height: 19px;
  color: #000000;
  margin: 0px;
  margin-bottom: 5px;
}
.appointment__adress{
  @include Rubik300;
  font-size: 14px;
  line-height: 20px;
  color: #000000;
  width: 285px;
  margin: 0px;
  margin-bottom: 5px;
}
.appointment__img{
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
}
.appointment__info{
  display: flex;
  align-items: center;
}
.doctor{
  margin-left: 10px;
}
.doctor__name{
  @include Rubik500;
  font-weight:bold;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin: 0px;
  margin-bottom: 5px;
}
.doctor__type{
  @include Rubik;
  font-size: 14px;
  line-height: 17px;
  color: #EBE7FF;
  margin: 0px;
}
.appointment__button{
  @include Rubik500;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  color: #FFFFFF;

  background: $button-color;
  border: none;
  border-radius: 5px;
  width: 98px;
  height: 40px;
  position: absolute;
  bottom: 20px;
  right: 20px;
}
</style>
