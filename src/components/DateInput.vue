<template lang="pug">
  .datepicker__input(
    @click="inputClick"
    data-qa='datepickerInput'
    :class="inputClass"
    v-text="inputDate ? inputDate : i18n[inputDateType]"
    :tabindex="tabIndex"
  )
</template>

<script>

export default {
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
    inputDate: {
      type: String,
      default: null,
    },
    inputDateType: {
      type: String,
      default: 'check-in'
    },
    singleDaySelection: {
      type: Boolean,
      default: false,
    },
    showDatepicker: {
      type: Function,
      required: true,
    },
    i18n: {
      type: Object,
      required: true,
    },
    focusedInput: {
      type: Boolean,
      default: ''
    },
  },

  computed: {
    inputClass() {
      return {
        'datepicker__input--is-active': this.isOpen && this.inputDate == null,
        'datepicker__input--single-date': this.singleDaySelection,
        'datepicker__input--is-focused': this.focusedInput,
        'datepicker__input--no-value': this.inputDate == null
      };
    },
    tabIndex() {
      return this.inputDateType === 'check-in' ? 0 : -1;
    }
  },

  methods: {
    inputClick(){
      this.inputDateType === 'check-in' ? this.showDatepicker('from') : this.showDatepicker('to')
    }
  }
};
</script>
