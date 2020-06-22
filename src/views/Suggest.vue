<template>
  <div class=Suggest>
      <Search @newData="getData"/>
      <div class="Suggest__result">
        <div class="Suggest__result-item" v-for="suggestItem in suggestData" v-bind:key="suggestItem[0]">
        {{suggestItem[0]}}
      </div>
      </div>

  </div>

</template>

<script>
import Search from '@/components/Search.vue'
export default {
  components: {
    Search
  },
  data() {
    return {
      suggestData: []
    }
  },
  methods: {
    getData(data) {
      console.log('this is a data from suggest:')
      console.log(data);
      this.suggestData = data;  
    }
  },
  props: {
    
  },
  watch: {

  }
}
</script>
<style lang="scss">
  .Suggest {
    margin: 4px;
    &__result{
      display: flex;
      flex-wrap: wrap;
      &-item {
        font-size: 16px;
        line-height: 20px;
        padding: 16px 12px;
        background-color: #f5f5f5;
        border-radius: 8px;
        margin-top: 8px;
        margin-left: 8px;
      }
    }
  }
</style>
