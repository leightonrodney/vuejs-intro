<script setup>

const companyName = 'YF Bank';

const currencies = {
  countries:{
    canada: {
      countryName: 'Canada',
      code: 'CAD',
      rate: 1.3
    },
    unitedKingdom: {
      countryName: 'UK',
      code: 'GBP',
      rate: 1.9,
    },
    unitedStatesOfAmerica: {
      countryName: 'USA',
      code: 'USD',
      rate: 2.1
    }
  },
};

const menuItems = [
  {
    menuItemName: 'Home',
    menuItemURL: 'https://google.com/',
    menuItemTitle: 'Visit home'
  },
  {
    menuItemName: 'My Account',
    menuItemURL: 'https://maps.google.com/',
    menuItemTitle: 'My Account details here'
  },
  {
    menuItemName: 'Transfers',
    menuItemURL: 'https://apple.com/',
    menuItemTitle: 'My Transfers are here!'
  },
  {
    menuItemName: 'Contact Us',
    menuItemURL: 'https://yahoo.com/',
    menuItemTitle: 'Support available 24/7.'
  },
];

const bannerImg = 'https://plus.unsplash.com/premium_photo-1664442782465-4aeb479c41b9?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8ZmFtaWx5JTIwcGxheWluZyUyMGluJTIwYSUyMHBhcmt8ZW58MHx8MHx8fDA%3D';
const bannerHeader = 'Save for the future.';
const interestPercentage = 1.2;
const bannerSubHeading = `With our new savings plan. ${interestPercentage * 2}% per annum.`;
const acctBalance = 10;
const bannerBtnText = 'Learn more';
const bannerBtnURL = 'https://google.com/';

const bannerImg2 = 'https://images.unsplash.com/photo-1713947504603-44cd607b83f1?q=80&w=1932&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D';
const bannerHeader2 = 'New rates!';
const bannerSubHeading2 = `With our new chequing account. ${interestPercentage}% per annum.`;
const bannerBtnURL2 = 'https://apple.com/';

const bannerHeight = 250;
const bannerWidth = 300;

</script>

<template>

  <main>

    <header>
      <a class="logo" href="#">{{ companyName }}</a>
      <ul class="navigation">
        <li v-for="({ menuItemName, menuItemURL, menuItemTitle }) in menuItems"><a target="_blank" :title="menuItemTitle" :href="menuItemURL">{{ menuItemName }}</a></li>
      </ul>
    </header>

    <ol class="currencies">
      <li v-for="({ countryName, code, rate  }) in currencies.countries">{{ countryName + ': ' + code }} - ${{ rate }}</li>
    </ol>

    <div v-if="acctBalance <= 500" class="banner">
      <img :src="bannerImg" :height="bannerHeight" :width="bannerWidth" alt="" />
      <div class="text-bg"> 
        <h3>{{ bannerHeader }}</h3>
        <p>{{ bannerSubHeading }}</p>
        <a class="banner-btn" target="_blank" :href="bannerBtnURL">{{ bannerBtnText }}</a>
      </div>
    </div>
    <div v-else class="banner">
      <img :src="bannerImg2" :height="bannerHeight" :width="bannerWidth" alt="" />
      <div class="text-bg"> 
        <h3>{{ bannerHeader2 }}</h3>
        <p>{{ bannerSubHeading2 }}</p>
        <a class="banner-btn" target="_blank" :href="bannerBtnURL2">{{ bannerBtnText }}</a>
      </div>
    </div>

  </main>

</template>

<style scoped>

  * {
    font-family: Arial, Helvetica, sans-serif;
  }

  main {
    width: 960px;
    margin: 0 auto;
    padding: 30px 15px;
    position: relative;
  }

  header{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    color: #008A00;
    text-decoration: none;
    font-size: 38px;
    font-weight: bold;
    margin-bottom: 30px;
    position: relative;
  }

  .navigation{
    margin: 0;
    padding: 0;
    list-style-type: none;
    display: flex;
    gap: 30px;
  }

  .navigation a{
    color: #008A00;
    text-decoration: none;
    font-weight: bold;
  }

  .currencies {
    margin: 30px 0;
  }

 .banner {
  border: 1px solid #008A00;
  display: flex;
  flex-direction: column;
  margin: 30px 0 0 0;
  padding: 0;
  position: relative;
  width: 300px;
  height: 250px;
 }

 .banner img {
  display: block;
  position: absolute;
  top: 0;
  left: 0;
 }

 .text-bg {
  background-color: #008A00;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  position: absolute;
  bottom: 0;
  width: 100%;
 }

 h3, p, a{
  margin: 0;
  padding: 0;
  color: #FFF;
 }

 p {
  font-size: 12px;
 }

 .banner-btn{
  display: block;
  font-size: 12px;
  text-decoration: none;
  padding: 15px 30px;
  border-radius: 6px;
  border: 1px solid #FFF;
  margin-top: 10px;
  margin-bottom: 10px;
 }



</style>
