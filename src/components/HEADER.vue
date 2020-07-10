<template>
    <header>
        <div class="memu">
            <p class="nenuText">Калькулятор</p>
        </div>
        <div class="text-devtools">
            НАСТРОЙКИ
        </div>
    </header>
</template>
<script>
// import leftMenu from './component-header/left-menu.vue'
// import menuLinks from './components/component-header/menu-links.vue'
// import rightButton from './components/component-header/right-button.vue'
export default {
    name: 'HEADER',
    data(){
        return{
            // n:'Калькулятор'
        }
    }
    ,
    method:{
        lol34(){
            // return false
            // console.log("yu")
        }
    },
    components:{
        // leftMenu,
        // menuLinks,
        // rightButton
    }
}
</script>
<style lang="css">
    .text-devtools{
        cursor: pointer;
        padding: 5px;
        border-radius: 5px;
        background-color: #fff;
        transition: all 1s;
    }
    .text-devtools:hover{
        border-radius: 14% 86% 7% 93% / 82% 11% 89% 18% ;
        background-color: #849986;
        color:#E5DED3
    }
    .nenuText:hover{
        background-color: #849986;
        color:#E5DED3;
        border-radius: 14% 86% 7% 93% / 82% 11% 89% 18% ;

    }
    header{
        /* width: 100%; */
        background-color: #D6CAB9;
        padding: 3px 5px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-weight: 900;
        font-size: 24px;
        color: #BE7E5A;
    }
    .btn-menu p{
        margin-top: -10px;
    }
    .btn-menu{
        background-color: #6A423B;
        width: 40px;
        height: 40px;
        border-radius: 5px;
        display: flex;
        align-items: center;
        font-weight: bold;
        font-size: 40px;
        flex-direction: column;
        justify-content: space-evenly;
        
    }
    .nenuText{
        margin-right: 8px;
        font-weight: bold;
        text-transform: uppercase;
        padding: 5px;
        border-radius: 5px;
        background-color: #fff;
        transition: all 1s;

    }
    .memu{
        display: flex;
        align-items: center;
        /* background-color: #6A423B; */
        padding: 3px;
        border-radius: 5px;
        cursor: pointer;
        overflow: hidden;
        transition: all 7s;
    }
</style>