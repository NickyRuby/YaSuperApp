<template>
  <div class="Widgets">
    <div class="Widget">
      <div class="Widget__tabs">
        <div :style="setActive" 
          v-for="tab in tabs" :key="tab" 
          :class="['Widget__tabs-item', {active: activeTab === tab.name}]" 
          @click="activeTab = tab.name">{{tab.name}} </div>
      </div>
      <div class="Widget__cards">   
        <WidgetCard :sourceIcon="widgetData[0].sourceIcon" :sourceName="widgetData[0].sourceName" :cardTitle="widgetData[0].cardTitle" />
        <CoronaWidget />
      </div>
    </div>
  </div>
</template>

<script>
import CoronaWidget from "@/components/CoronaWidget.vue";
import WidgetCard from "@/components/WidgetCard.vue";
export default {
  components: {
    CoronaWidget, WidgetCard
  },
  data() {
    return {
      activeTab: 'Важное',
      tabs: [
        {name: 'Важное', isActive: false},
        {name: 'Коронавирус', isActive: false},
        {name: 'Новости', isActive: false},
        {name: 'Котировки', isActive: false}
      ],
      widgetData: [
          { 
              sourceIcon: 'https://sun1-20.userapi.com/ynoXmmMlUIgpplZ9krLihqIbQ_WnS8ynZ8ewjQ/xK33ESMfgF0.jpg?ava=1',
              sourceName: 'Оперштаб Москвы',
              cardTitle: 'В Москве скончались 48 пациентов с коронавирусом'
          }
      ],
    };
  },
  props: {
    icon: String,
    title: String,
  },
  computed: {
    setActive() {
      return 
    }
  }
};
</script>

<style lang="scss">
.Widget {
  background-color: white;
  margin: 24px 4px;
  padding: 16px 10px;
  padding-right: 0;
  border-radius: 24px;

  &__tabs {
    display: flex;
    width: 100%;
    margin-bottom: 8px;
    overflow: scroll;
    margin-right: -16px;
    &::-webkit-scrollbar {
      display: none;
    }

    &-item {
      font-size: 14px;
      line-height: 18px;
      padding: 8px 12px;
    }
  }
  &__cards {
    display: flex;
    margin-left: -10px;
    margin-right: 1px;
    overflow: auto;
    padding-bottom: 4px;
    &::-webkit-scrollbar {
      display: none;
    }
    &-item {
      padding: 12px;
      background: #ffffff;
      border: 1px solid #f0f1f5;
      box-sizing: border-box;
      box-shadow: 0px 4px 16px rgba(223, 226, 226, 0.25);
      border-radius: 16px;
      width: 230px;
      flex-basis: 240px;
      flex-shrink: 0;
      margin-left: 16px;
      &-source {
        display: flex;
        &-icon {
          width: 16px;
          height: 16px;
          margin-right: 4px;
        }
        &-title {
          font-size: 12px;
          line-height: 16px;
          color: grey;
          font-weight: 500;
        }
      }
      &-title {
        font-size: 14px;
        color: #333;
        line-height: 18px;
        margin-top: 4px;
      }
      &-date {
        font-size: 12px;
        color: #333;
        line-height: 16px;
        margin-top: 4px;
        color: gray;
      }
    }
  }
}
.active {
  background-color: #FBE578;
  border-radius: 16px;
}
</style>
