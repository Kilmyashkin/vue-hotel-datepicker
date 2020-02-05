<template>
  <div id="app" style="text-align: left; padding: 10vw">
    <div>

      <div class="box">
        <h3>Allow check-in and check-out on the same day</h3>
        <DatePicker
          :minNights="0"
          :i18n="{
            night: 'Night',
            nights: 'Nights',
            'day-names-short': ['вс', 'пн', 'вт', 'ср', 'чт', 'пт', 'сб'],
            'day-names': ['Dom', 'Seg', 'Ter', 'Qua', 'Qui', 'Sex', 'Sab'],
            'check-in': 'Туда',
            'check-out': 'Обратно',
            'month-names': ['January', 'Февра', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
          }"
          format="D MMM, ddd"
        />
      </div>
    </div>
    </div>
  </div>
</template>

<script>
  import DatePicker from 'components/DatePicker.vue';

  export default {
    components: {
      DatePicker
    },

    data() {
      return {
        ptPT: {
          night: 'Noite',
          nights: 'Noites',
          'day-names': ['Dom', 'Seg', 'Ter', 'Qua', 'Qui', 'Sex', 'Sab'],
          'check-in': 'Chegada',
          'check-out': 'Partida',
          'month-names': ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho', 'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro'],
        }
      };
    }
  };

</script>

<style>
  body,
  html {
    font-family: 'Source Sans Pro', sans-serif;
  }

  .box {
    width: 100%;
  }
</style>
