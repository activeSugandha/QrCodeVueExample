

<template>
<div class="content">
   <qrcode-vue :value="value" :size="size" level="H"></qrcode-vue>
</div>
</template>

<script>
 import QrcodeVue from 'qrcode.vue'

  export default {
    data() {
      return {
        value: 'https://google.com',
        size: 200,
        consentTypeTest: [
                    {
                        channelType: "Electronic Messaging",
                        primaryEmail: "haifa.al-ali@uk-halle.de.invalid",
                        secondaryEmail: "",
                        typeId: "a3C760000009CtXEAU"
                    },
                    {
                        channelType: "Analysis",
                        typeId: "a3C760000009CtX000"
                    },
                ], test: [
                    {
                        primaryEmail: 'haifa.al-ali@uk-halle.de.invalid',
                        secondaryEmail: "haifa.al-ali@uk-halle.de.invalid",
                        consentId: "a3C760000009CtXEAU",
                        date: "Wed May 23 2018 12:11:54 GMT+0530 (IST)"
                    },
                    {
                        primaryEmail: 'haifa.al-ali@uk-halle.de.invalid',
                        secondaryEmail: "priyesh.walunj-consultant@alexion.com",
                        consentId: "a3C760000009CtXEAU",
                        date: "Wed May 23 2018 12:11:54 GMT+0530 (IST)"
                    }
                ]
      }
    },
    components: {
     QrcodeVue
    },
    computed: {

    }
   
  }
</script>
<style scoped>
.content{
  width: 900px;
  margin: 0px 20px;
  border: 1px solid green;
  border-radius: 9px;
  height: 500px;
  padding: 15px 25px;
}
</style>