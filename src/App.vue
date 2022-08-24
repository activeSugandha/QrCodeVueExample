<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import qrCode from './components/qrCode.vue'
import ConsentComp from './components/consent.vue'
</script>

<template>
  <header class="custom-header">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <span class="title">Electronic Consent Capture </span>
 </header>
 <div class="wrapper">
     <ConsentComp />
      <qrCode />
    </div>

</template>

<style scoped>
.custom-header {
 border: 1px solid #1fa91f;
    border-radius: 9px;
    padding: 10px;
    line-height: 1px;
    height: 72px;
    margin-bottom: 10px;
    
}
.title{
      font-size: 33px;
      color: green;
    }
.logo {
      width: 61px;
    margin: 20px;
  display: block;
  margin: 0 auto 2rem;
}
.wrapper{
   display: flex;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
