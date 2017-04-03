<template>
  <div>
    <mu-raised-button @click="openBottomSheet"
                      label="打开选择器" />
    <h3>{{area}}</h3>
    <area-picker :openPicker="open"
                 @changed="pickerChanged"
                 @closed="pickerClosed"></area-picker>
  </div>
</template>

<script>
import AreaPicker from './AreaPicker'
import raisedButton from 'muse-components/raisedButton'
export default {
  components: {
    AreaPicker,
    'mu-raised-button': raisedButton
  },
  data() {
    return {
      open: false,
      area: ''
    }
  },
  methods: {
    openBottomSheet() {
      this.open = true;
    },
    pickerChanged(address) {
      this.area = address.join('/')
    },
    pickerClosed() {
      this.open = false;
    }
  }
}
</script>