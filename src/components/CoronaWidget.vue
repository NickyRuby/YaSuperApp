<template>
    <div class="WidgetCorona__cards-item">
        <div class="WidgetCorona__cards-item-source">
            <div class="WidgetCorona__cards-item-source-icon"></div>
            <div class="WidgetCorona__cards-item-source-title">Индекс самоизоляции</div>
        </div>
        <div class="WidgetCorona__cards-item-data">
            <div class="WidgetCorona__cards-item-data-mark">4.3</div>
            <div class="WidgetCorona__cards-item-data-title">На улице <br>мало людей</div>
        </div>
        <!-- <div class="WidgetCorona__cards-item-date">Cегодня</div> -->
    </div>
</template>

<script>    
</script>

<style lang="scss">
.WidgetCorona {
    background-color: white;
    margin: 24px 4px;
    padding: 15px;
    border-radius: 24px;

    &__cards {

        &-item {
            padding: 12px;
            background: #FFFFFF;
            border: 1px solid #F0F1F5;
            box-sizing: border-box;
            box-shadow: 0px 4px 16px rgba(223, 226, 226, 0.25);
            border-radius: 16px;
            width: 230px;
            flex-basis: 240px;
            flex-shrink: 0;
            margin-left: 8px;

            &-source {
                display: flex;
                &-icon {
                    width: 16px;
                    height: 16px;
                    margin-right: 4px;
                    background: url('https://yastatic.net/s3/front-maps-static/front-maps/_/8eb9b398c247b7bfa3088a7a16dfd7d8.svg') center center #4f8bfa;
                    border-radius: 50%;
                    background-size: 14px 14px;
                }
                &-title {
                    font-size: 12px;
                    line-height: 16px;
                    color: grey;
                    font-weight: 500;

                }
            }
            &-data {
                display: flex;
                align-items: center;
                margin-top: 6px;

                &-mark {
                font-size: 28px;
                line-height: 40px;
                font-weight: 500;
                padding: 0px 16px 0 14px;
                background-color: #23c523;
                color: white;
                border-radius: 24px;
                }
                &-title {
                font-size: 14px;
                line-height: 16px;
                margin-left: 8px;
                }
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