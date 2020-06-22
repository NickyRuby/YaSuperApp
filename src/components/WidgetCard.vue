<template>
        <div class="Widget__cards-item">
          <div class="Widget__cards-item-source">
            <div class="Widget__cards-item-source-icon" :style="getSourceIcon"></div>
            <div class="Widget__cards-item-source-title">{{sourceName}}</div>
          </div>
          <div class="Widget__cards-item-title">{{cardTitle}}</div>
          <div class="Widget__cards-item-date">{{date}}</div>
        </div>
</template>

<script>
export default {
  props: {
    sourceIcon: String,
    sourceName: String,
    cardTitle: String,
    date: String
  }, 
  computed: {
        getSourceIcon() {
            return {
                backgroundImage: `url(${this.sourceIcon})`
            }
        }
    },
};
</script>

<style lang="scss">
.Widget {
    &__cards-item {
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
        align-items: center;
        &-icon {
          width: 20px;
          height: 20px;
          background-size: contain;
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
</style>
