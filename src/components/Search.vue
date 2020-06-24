<template>
    <div class="App__search">
      <div class="App__search-arrow">
        <div class="App__search-arrow-shape">
            <div class="App__search-arrow-shape-content">
              <router-link :to="{name: 'Suggest'}" class="App__search-arrow-shape-content-suggest"></router-link>
              <div class="App__search-arrow-shape-content-yalogo"></div>
              <div class="App__search-arrow-shape-content-input">
                <input v-model="searchText" @keyup="getSuggestData" placeholder="Что ищем?">
              </div>
              <div class="App__search-arrow-shape-content-scan"></div>
            </div>
        </div> 
        <div class="App__search-arrow-shape-right-arrow"></div>
      </div>
    </div>  
</template>

<script>
  export default {
    data() {
      return {
        searchText: '',
        suggestData: []
      }
    }, 
    methods: {
      getSuggestData() {
        const url = `https://yandex.ru/suggest/suggest-endings?&srv=morda_ru_touch&wiz=TrWth&uil=ru&fact=1&v=4&icon=1&mob=1&tpah=1&sn=7&full_text_count=5&bemjson=0&platform=touch&verified_nav=1&rich_phone=1&history=1&use_favicon=1&mt_wizard=1&yu=8016961061590418853&lr=213&safeclick=1&skip_clickdaemon_host=1&a=0&svg=1&part=${this.searchText}&pos=5&suggest_reqid=801696106159041885335316907463862&hs=0`;
        fetch(url).then((res) => res.json()).then((data) => {
          console.log(data[2]);
          this.suggestData = data[2];
          console.log(this.suggestData);
          this.$emit("newData",this.suggestData);
          this.suggestData = [];  

        });  
      }
    }
  }
</script>

<style lang="scss">
.App__search {  
  &-arrow {
    // width: 100%;
    // height: 40px;
    // border: 1px solid #c4c4c4;
    // border-radius: 4px;
    display: flex;

    &-shape {
      width: 95%;
      height: 58px;
      // background: url("../assets/search-arrow.svg");
      background-repeat: no-repeat;
      // padding: 16px;
      box-sizing: border-box;
      border-radius: 12px 0px 0px 12px;
      border-left: 3px solid #F7CE46;
      border-top: 3px solid #F7CE46;
      border-bottom: 3px solid #F7CE46;
      &-content {
        display: flex;
        position: relative;
        width:100%;
        background-color: #fff;
        border-radius: 12px 0px 0px 12px;   
        &-suggest {
          position: absolute;
          top: 0;
          right: 0;
          left: 0;
          bottom: 0;
          width: 100%;
        }
        &-yalogo {
          width: 24px;
          height: 24px;
          margin: 14px 0px 14px 14px;
          background: url('../assets/yalogo.svg');
        }
        &-input {
          font-size: 14px;
          line-height: 24px;
          text-align: center;
          width: 80%;
          color: gray;
          margin-left: 4px;
          position: relative;
        }
        &-scan {
          width: 24px;
          height: 24px;
          background: url('../assets/scan.svg');
          margin: 14px 0px 14px 14px;
        }
      }
    &-right-arrow{
      background: url('../assets/right-search-arrow.svg');
      width: 32px;
      background-repeat: no-repeat;
     } 
    }
  }
    &-services {
      display: flex;
      justify-content: space-between;
      align-items: left;
      margin-top: 8px;
      &-item {
        padding: 12px 16px;
        background-color: #efefef;
        border-radius: 16px;
        font-size: 13px;
        color: rgb(94, 91, 91);
        text-align: center;
        width: auto;
      }
    }
  input {
    font-size: 14px;
    text-align: center;
    border: 0;
    padding: 16px 0px;
    width: 100%;
    box-sizing: border-box;
    outline: none;
  }
}

</style>