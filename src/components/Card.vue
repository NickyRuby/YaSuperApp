<template>
  <div class="Cards">
    <div class="Cards__item">
      <div class="Cards__item-app">
        <div class="Cards__item-app-icon" :style="getIcon()"></div>
        <div class="Cards__item-app-meta">
          <div class="Cards__item-app-meta-name">{{ source }}</div>
          <div class="Cards__item-app-meta-submeta">4.8 • Все о мире кино</div>
        </div>
      </div>
      <div class="Cards__item-cover" :style="getCover()"></div>
      <div class="Cards__item-info">
        <div class="Cards__item-info-title">{{ title }}</div>
        <div class="Cards__item-info-about">{{ about }}</div>
        <div class="Cards__item-info-meta">
          <div class="Cards__item-info-meta-date">{{ date }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    about: String,
    source: String,
    sourceIcon: String,
    cover: String,
    date: String,
  },
  computed: {},
  methods: {
    getIcon() {
      return {
        backgroundImage: `url(${this.sourceIcon})`,
      };
    },
    getCover() {
      return {
        backgroundImage: `url(${this.cover})`,
      };
    },
  },
};
</script>

<style lang="scss">
.Cards {
  margin-top: 24px;
  margin-bottom: 16px;
  &__item {
    width: 100%;
    background: #ffffff;
    border: 1px solid #eeefef;
    box-sizing: border-box;
    border-radius: 16px;
    // margin-top: 25px;
    margin-bottom: 16px;
    &-app {
      display: flex;
      padding: 12px;
      &-icon {
        width: 40px;
        height: 40px;
        border-radius: 12px;
        background-color: #f0f1f5;
        background-size: contain;
      }
      &-meta {
        margin-left: 12px;
        padding-top: 4px;
        &-name {
          font-size: 14px;
          line-height: 18px;
        }
        &-submeta {
          font-size: 12px;
          line-height: 16px;
          color: #999595;
        }
      }
    }

    &-cover {
      height: 200px;
      // background: url('../assets/rick&morty.png');
      background-size: cover;
      border-radius: 16px ;
    }
    &-info {
      margin: 16px;
      &-title {
        font-weight: 500;
        font-size: 16px;
        line-height: 16px;
      }
      &-about {
        margin-top: 8px;
        font-size: 12px;
        line-height: 16px;
        color: #999595;
      }
      &-meta {
        margin-top: 8px;
        &-date {
          font-size: 12px;
          line-height: 16px;
          color: #333;
        }
      }
    }
  }
}
</style>
