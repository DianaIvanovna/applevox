<template>
  <section class="main">
    <h3 class="main__title"  v-if="!flagHiddenCard" >Записи на прием</h3>
    <h3 class="main__title"  v-else @click="openElCard">
      <img src="@/assets/images/arrow.svg" alt="icon arrow" class="main__icon">Мои записи</h3>
    <!--  список записей на прием -->
    <div class="main__container"
      :class="{main__container_hiddenCard: flagHiddenCard }">
      <AppointmentsList class="AppointmentsList"
        :horizontallyAppointmets="horizontallyAppointmets"
        @hidecard = "hideElCard($event)"/>
      <!--  электронная карта -->
      <ElectronicCard
        v-if="!flagHiddenCard"/>
      <!-- Календарь -->
      <Calendar
      :dates="dates"
      v-if="flagHiddenCard"/>
    </div>
  </section>
</template>
<script>
import AppointmentsList from '@/components/AppointmentsList.vue';
import ElectronicCard from '@/components/ElectronicCard.vue';
import Calendar from '@/components/Calendar.vue';

export default {
  components: {
    AppointmentsList, ElectronicCard, Calendar,
  },
  data() {
    return {
      flagHiddenCard: false,
      horizontallyAppointmets: false,
      dates: [],
    };
  },
  methods: {
    hideElCard(event) {
      this.flagHiddenCard = event.flag;
      this.horizontallyAppointmets = event.flag;
      this.dates = event.dates;
    },
    openElCard() {
      this.flagHiddenCard = false;
      this.horizontallyAppointmets = false;
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
.main__container_hiddenCard{
  display: flex;
  justify-content: space-between;
  .AppointmentsList{
    margin-right: 40px;
  }
}
.main__icon{
  margin-right: 15px;
}
.main__title{
  @include Rubik;
  font-size: 16px;
  line-height: 19px;
  color: #000000;
  margin: 15px 0px;
  margin-left: 40px;
}
</style>
