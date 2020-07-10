<template>
  <div id="app">
    <!-- <HEADER/> -->
      <div class="calc">
        <div @click="copu_pocht" class="btn-gmail">
          cpa@alfabank.ru
        </div>
        <div class="zp">
          <input v-model="zp_v" placeholder="ЗП" class="zp_input" type="number">
          <div @click="copu_zp" class="btn-otv">
            <template v-if="zp_v==''">Введите число!</template>
            <template v-else>{{number_zp}} руб.</template>
          </div>
        </div>
        <div class="pronch_snyat">
          <input v-model="proch" placeholder="% - за снятие" class="zp_input" type="number">
          <div @click="copu_proch" class="btn-otv">
            <template v-if="proch==''">Введите число!</template>
            <template v-else>{{pronch_for_snat}}</template>
          </div>
        </div>
      </div>
    <FOOTER/>
  </div>
</template>

<script>
import FOOTER from './components/FOOTER.vue';
export default {
  name: 'App',
  data(){
    return{
      zp_v:'',
      proch:''
    }
  },
  components: {
    FOOTER
  },
  methods:{
    copu_zp(){
      function copyStringToClipboard (str) {
      var el = document.createElement('textarea');
      el.value = str;
      el.setAttribute('readonly', '');
      el.style.position = 'absolute';
      el.style.left = '-9999px';
      document.body.appendChild(el);
      el.select();
      document.execCommand('copy');
      document.body.removeChild(el);

      }
      copyStringToClipboard(this.number_zp);
    },
    copu_proch(){
      function copyStringToClipboard (str) {
      var el = document.createElement('textarea');
      el.value = str;
      el.setAttribute('readonly', '');
      el.style.position = 'absolute';
      el.style.left = '-9999px';
      document.body.appendChild(el);
      el.select();
      document.execCommand('copy');
      document.body.removeChild(el);
      }
      copyStringToClipboard(this.pronch_for_snat);
    },
    copu_pocht(){
      function copyStringToClipboard (str) {
      var el = document.createElement('textarea');
      el.value = str;
      el.setAttribute('readonly', '');
      el.style.position = 'absolute';
      el.style.left = '-9999px';
      document.body.appendChild(el);
      el.select();
      document.execCommand('copy');
      document.body.removeChild(el);
      }
      copyStringToClipboard('cpa@alfabank.ru');
    },
  },
  computed: {
    number_zp(){
      return Number(this.zp_v) - Number(this.zp_v) * 0.13;
    },
    pronch_for_snat(){
      let PR = Number(this.proch)
      let real_PR = Number(this.proch)
      if(PR<=50000){
        return 0 + ', т.к 50.000р'
      }
      real_PR = (PR - 50000) * 0.059;
      if(real_PR<=500){
        return "500р - т.к минимально 500р. \n \n"+
        real_PR+" р. = 5.9%"
      }
      return real_PR + " р. = 5.9%"
    }
  },
}
</script>



<style>
  body{
    background-color: #D3CDBE;
    /* background-color: #D3DDDB; */

  }
:root {
  --main-bg-color: #414042;
  --fns: 20px;
  --wdth: 150px;
  --hight: 50px;
  --colo:#EAE3DD ;
}
  .pronch_snyat{
    margin: 0 auto;
    width: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-weight: 900;
    margin-top: 20px;
  }
  .btn-gmail{
    background-color: red;
    text-align: center;
    width: 150px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 10px auto;
    border-radius: 5px;
    cursor: pointer;
    background-color: var(--main-bg-color);
    font-size: var(--fns);
    width: var(--wdth);
    height: 40px;
    font-weight: 900;
    color: var(--colo)
  }
  .btn-otv{
    background-color: var(--main-bg-color);
    font-size: var(--fns);
    min-width: var(--wdth);
    min-height: var(--hight);
    text-align: center;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    cursor: pointer;
    border-radius: 5px;
    font-weight: 900;
    color: var(--colo)
  }
  .zp{
    margin: 0 auto;
    width: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
    
    
  }
  .zp_input{
    width: 100px;
    border: none;
    outline: none;
    /* background-color: red; */
    background-color: var(--main-bg-color);

    /* height: 30px; */
    width: 150px;
    font-size: 18px;
    margin-bottom: 8px;
    height: 40px;
    background-color: var(--main-bg-color);
    /* text-align: center; */
    width: 150px;
    /* height: 21px; */
    border-radius: 5px;
    color: var(--colo);
    border-bottom: 5px solid #A17C6A;
    border-right: 5px solid #A17C6A;
  }
  .zp_input::placeholder{
    /* background-colorgb(201, 49, 49)fff; */
    padding: 5px;
    font-size: 18px;
    color: var(--colo);

  }

*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
html,body{
  /* width: 100%; */
  /* height: 100%;  */
}
#app{
  /* width: 100%; */
  /* height: 100%; */
  /* background-color: red; */
  /* display: flex;
  flex-direction: column;
  justify-content: space-between; */
}
</style>
