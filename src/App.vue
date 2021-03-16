<template>
  <div id="app">
    <input type="text" v-model="zipcode" maxlength="7" />
    <button @click="created">住所自動入力</button>  
    <p>Address:{{addressData}}</p>
</div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      zipcode: null,
      addressData: "",
    };
  },
  methods: {
    async created() {
      const response =await axios.get (
       'https://apis.postcode-jp.com/api/v4/postcodes/' + this.zipcode + '?apiKey=Uq8U252RKyTgec4pbyeLqa4DANzerj0LcSa4N6q'
        );
        this.addressData=response['data'][0]['allAddress']
    }
  }
};
</script>

