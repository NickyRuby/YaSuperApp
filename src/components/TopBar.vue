<template>
    <div class="App__top-bar">
      <div class="App__top-bar-location">
          <div class="App__top-bar-location-icon"></div>
          <div class="App__top-bar-location-text">Moscow, 5 May</div>
      </div>
      <div class=App__top-bar-right>
        <div class="App__top-bar-right-bell"></div>
        <div class="App__top-bar-right-avatar"></div>
      </div>
    </div>
</template>

<script>
</script>

<style lang="scss">
  .App__top-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 0;

    &-location {
      display: inline-flex;
      height: 16px;
    
        &-icon {
        width: 16px;
        height: 16px;
        background: url('../assets/location.svg');
        background-repeat: no-repeat;
        background-color: (0, 0, 0, 0.5);
        }

        &-text {
          margin-left: 4px;
          line-height: 16 px;
          font-size: 13px;
          color: rgba(0, 0, 0, 0.5);

        }
    }
    &-right {
          display: flex;
          align-items: center;
    }

    &-right-bell {
      background-color: pink;
      width: 16px;
      height: 16px;
      background: url('../assets/bell.svg');
      background-size: cover;
      background-repeat: no-repeat;
      background-size: cover;
      margin-right: 16px;
    }
    &-right-avatar {
        width: 32px;
        height: 32px;
        background-color: pink;
        border-radius: 50%;
        background: url('https://center.yandex-team.ru/api/v1/user/nktl96/photo/300.jpg');
        background-size: cover;
        background-repeat: no-repeat;
        background-size: cover;
        border: 1px solid #efefef;
    }
  }
</style>