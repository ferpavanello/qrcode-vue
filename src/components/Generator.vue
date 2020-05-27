<template>
  <div class="generator">
    <h1>{{ msg }}</h1>
    <div>
      <input
        class="input-info"
        type="text"
        placeholder="Put your info to be converted"
        @input="onChange"
      />
    </div>
    <div class="wrap-qrcode">
    <picture>
      <img v-if="newQRCode" :src="newQRCode">
    </picture>
    </div>
  </div>
</template>

<script>
import QRCode from 'qrcode'

export default {
  name: 'Generator',
  props: {
    msg: {
      type: String,
      default: 'Ops...'
    }
  },
  data () {
    return {
      newQRCode: ''
    }
  },
  methods: {
    onChange (event) {
      const targetValue = event && event.target && event.target.value
      if (targetValue) {
        this.generateQRCode(targetValue)
      }
    },
    generateQRCode (newValue = '') {
      const options = {
        width: 500,
        margin: 0
      }
      QRCode.toDataURL(newValue, options)
        .then(img => this.newQRCode = img)
    }
  }
}
</script>

<style>
.input-info {
  display: inline-block;
  background: transparent;
  border: 1px solid #000;
  font-family: Arial, "Roboto", sans-serif;
  font-size: 20px;
  padding: 8px;
  width: 358px;
  vertical-align: bottom;
}

.wrap-qrcode {
  margin-top: 40px;
}
</style>