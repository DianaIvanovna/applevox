<template>
  <v-row>
    <v-date-picker v-model="picker"
      color="#7761FF"
      locale="ru"
      :first-day-of-week="1"
      event-color="#50CAFF"
      :events="arrayEvents"
      no-title
      width="573"></v-date-picker>
  </v-row>
</template>
<script>
export default {
  props: ['dates'],
  data() {
    return {
      picker: new Date().toISOString().substr(0, 10),
      arrayEvents: this.dates,
    };
  },
};
</script>
<style lang="scss" scoped>
.v-date-picker-table .v-btn { color: green };
</style>
