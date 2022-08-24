<template>

 <div class="content">
   <div class="wrapper" v-for="item in resultConsent">
    <div v-if="item.channelType === 'Electronic Messaging'">
      <h3>{{item.channelType}}</h3>
      <div v-for= "val in item.MCconsent">
      <span v-if="val.consentValue>
        <span>{{val.consentValue}}</span>
         <input type='checkbox' id='val.consentId' v-model='val.optStatus'>
      </span>
      </div>
    </div>
   <div v-else>
    <h3>{{item.channelType}}</h3>
    <input type='checkbox' id='tom' v-model='item.optStatus'>
   </div>
  </div> 
 </div>
</template>

<script>

  export default {
    name: 'ConsentComp',
    data() {
      return {
        resultConsent : [],
       consentTypeTest: [
                    {
                        channelType: 'Electronic Messaging',
                        typeId: 'a3C760000009CtXEAU'
                    },
                    {
                        channelType: 'Analysis',
                        typeId: 'a3C760000009CtX000'
                    },
                ], MCConsent: [
                  {
                        consentSource: 'haifa.al-ali@uk-halle.de.invalid',
                        consentValue: 'haifa.al-ali@uk-halle.de.invalid',
                        consentId: 'a3C760000009CtXEAU',
                        date: 'Wed May 23 2018 12:11:54 GMT+0530 (IST)'
                    },
                     /*{
                        consentSource: 'haifa.al-ali@uk-halle.de.invalid',
                        consentValue: 'sugandha.singh@gmail.com',
                        consentId: 'a3C760000009CtXEAU',
                        date: 'Wed May 23 2018 12:11:54 GMT+0530 (IST)'
                    },
                    {
                        consentSource: 'haifa.al-ali@uk-halle.de.invalid',
                        consentValue: 'priyesh.walunj-consultant@alexion.com',
                        consentId: 'a3C760000009CtX000',//'a3C760000009CtXEAU',
                        date: 'Wed May 23 2018 12:11:54 GMT+0530 (IST)'
                    }*/
                ],
                Account : [
                  {
                    PersonEmail: 'haifa.al-ali@uk-halle.de.invalid',
                    Email_User_Input_2__c: ''
                  }
                ]
      }
    },
    components: {
    
    },
    computed: {

    },
    mounted(){
        this.getConsentData()
    },
    methods : {
      getConsentData(){
        console.log('Consent Type',this.consentTypeTest);
        console.log('MC Consent',this.MCConsent);
       
        /*this.resultConsent = this.consentTypeTest.map(item => Object.assign({}, item, this.MCConsent.filter(val => {
         if(val.consentId == item.typeId){
            item.consentStatus = 'Granted'
          }else item.consentStatus = 'Not Granted'
          return item
        })))
        //this.consentTypeTest.map((item) => Object.assign( {}, item, this.MCConsent.filter(item2 => item2.consentId == item.typeId )));
        console.log('result consent ',this.resultConsent);*/
        
      /* let result =  this.resultConsent.forEach((item) => this.MCConsent.map(val =>{
        
          if(val.consentId == item.typeId){
             console.log('item',item);
            item.consentStatus = 'Granted'
          }else item.consentStatus = 'Not Granted'
         
        }))*/
        /*let result =  this.consentTypeTest.map(item => Object.assign({}, item, this.MCConsent.filter(val => {
      
         if(val.consentId == item.typeId){
            item.consentStatus = 'Granted'
          }else item.consentStatus = 'Not Granted'
          return item
        })))
        console.log('result consent ',result)*/
        this.resultConsent = this.consentTypeTest.map(item => {
          let result = this.MCConsent.filter(val => val.consentId == item.typeId)
          console.log('final result', result)
          if(result.length >0){
            result.map(i => {
              i.consentStatus = 'Granted'
              i.optStatus = true})
            item.MCconsent = result
             item.consentStatus = 'Granted'
              item.optStatus = true
          }else {
            item.consentStatus = 'Not Granted'
            item.optStatus = false}
          return item
        })
        console.log('Final value',this.resultConsent);
        
      }
    }
   
  }
</script>
<style>
.content{
  width: 900px;
    border: 1px solid green;
    border-radius: 9px;
    height: 500px;
    padding: 15px 25px;
}
.content h3{
    border: 1px solid green;
    padding: 5px;
    background-color: #92c992;
}
.wrapper{
    border: 1px solid green;
    border-radius: 7px;
    height: 108px;
}
</style>
