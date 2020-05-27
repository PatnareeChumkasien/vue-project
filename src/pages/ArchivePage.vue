<template>
    <div>
        <CardList :item="archives"></CardList>
    </div>
</template>

<script>
import axios from 'axios'
import CardList from '../components/CardList.vue'
export default {
    name: 'ArchivePage',
    components: { 
        CardList 
    },
    async created(){
        const { data } = await axios.get('http://localhost:8080/#/archive') 
        this.archives = data
    },
    data(){
        return {
            archives: []
        }
    }
}
</script>