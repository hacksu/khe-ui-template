<template>
  <div id="container">
    <main-landing></main-landing>
    <info></info>
    <faq></faq>
    <kentmap></kentmap>
    
  </div>
</template>

<script>
import scrollto from 'vue-scrollto';
  
import mainLanding from './homeComponents/Main';
import info from './homeComponents/Info';
import faq from './homeComponents/FAQ';
import kentmap from './homeComponents/Map';

export default {
  name: 'Home',
  components: {
    mainLanding,
    info,
    faq,
    kentmap
  },
  data() {
    return {

    };
  },
  
  mounted: function() {
    if (this.$parent.scrollToEl !== '') {
      scrollto.scrollTo(this.$parent.scrollToEl, 300);
      this.$parent.scrollToEl = '';
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
  
  
  #container {
    text-align: center;
  }
  
  #logo {
    animation: fadein 1s linear;
    margin-top: 40px;
    margin-bottom: -60px;
    /* This margin makes the logo look more centered */
    margin-right: 25px;
  }
  
  #title {
    font-size: 35px;
  }
  
  #location {
    margin-top: -10px;
  }
  
  .mainBtn {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    padding: 20px 40px 20px 40px;
    background: white;
    font-size: 20px;
    border: solid black 2px;
    border-top-left-radius: 10% 20%;
    border-top-right-radius: 10% 20%;
    border-bottom-left-radius: 10% 20%;
    border-bottom-right-radius: 10% 20%;
    margin: 10px;
    transition-duration: .2s;
  }
  .mainBtn:hover {
    background: black;
    color: white;
    border: solid gray 2px;
  }
  
  
  @keyframes fadein {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  
  
</style>
