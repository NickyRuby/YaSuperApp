<template>
    <div class="service-item">
        <div class="service-item-logo" :style="picStyle"></div>
        <div class="service-item-text">{{title}}</div>
    </div>   
</template>

<script>
export default {
    props: {
        title: {
            default: 'Такси'
        },
        iconUrl: String,
    },
    computed: {
        picStyle() {
            return {
                backgroundImage: `url(${this.iconUrl})`
            }
        }
    },

}
</script>
 
<style lang="scss">
    
.service-item {
    flex: 1 0 21%;
    margin-top: 20px;

&-logo {
    width: 56px;
    height: 56px;
    background-color: white;
    border-radius: 16px;
    // background: url('../assets/services/efir.svg');
    background-size: cover;
    margin: auto;
    }
    &-text {
    width: 100%;
    font-size: 12px;
    text-align: center;
    margin-top: 4px;
    }
}

</style>