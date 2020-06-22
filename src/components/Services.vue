<template>
    <div class="Services">
        <ServiceItem v-for="service in services" v-bind:key="service.title" :title="service.title" :iconUrl="service.iconUrl" />
        <!-- <div class="Services_button">Все сервисы</div> -->
    </div> 
</template>

<script>
import ServiceItem from '@/components/ServiceItem.vue';
export default {
    components: {
        ServiceItem
    },
    data() {
        return {
            services: [
                { title: "Еда", iconUrl: "https://yastatic.net/s3/home/services/block/eda.svg" },
                { title: "Лавка", iconUrl: "https://yastatic.net/s3/home/services/block/lavka.svg" },
                { title: "Музыка", iconUrl: "https://yastatic.net/s3/home/services/block/music1.svg" },
                { title: "Эфир", iconUrl: "https://yastatic.net/s3/home/services/block/efir.svg" },
                { title: "Кинопоиск", iconUrl: "https://yastatic.net/s3/home/services/block/kinopoisk.svg" },
                { title: "Уроки", iconUrl: "https://yastatic.net/s3/home/services/block/uroki.svg" },
                { title: "Игры", iconUrl: "https://yastatic.net/s3/home/services/block/games.svg" },
                { title: "Едадил", iconUrl: "https://yastatic.net/s3/home/services/block/edadeal.svg" },
                
            ]
        }
    }        
}
</script>

<style lang="scss">
.Services {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    justify-content: space-around;  
    box-sizing: border-box;
}

</style>
