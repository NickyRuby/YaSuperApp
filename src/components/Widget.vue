<template>
  <div class="Widgets">
    <div class="Widget">
      <div class="Widget__tabs">
        <div class="Widget__tabs-item" v-for="tabName in tabs" v-bind:key="tabName">{{tabName}}</div>
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
      tabs: ['Важное', 'Коронавирус', 'Новости', 'Котировки'],
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
};
</script>

<style lang="scss">
.Widget {
  background-color: white;
  margin: 24px 4px;
  padding: 15px;
  padding-right: 0;
  border-radius: 24px;

  &__tabs {
    display: flex;
    width: 100%;
    overflow: scroll;
    margin-right: -16px;
    &::-webkit-scrollbar {
      display: none;
    }

    &-item {
      margin-right: 8px;
      font-size: 14px;
      line-height: 18px;
      font-weight: medium;
      padding: 8px;
    }
  }
  &__cards {
    display: flex;
    margin-top: 8px;
    margin-left: -16px;
    overflow: auto;
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
</style>
