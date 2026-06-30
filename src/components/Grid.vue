<template >
    <div>
        <button class="text-amber-900 font-bold shadow-amber-950 bg-amber-50 border border-amber-200 rounded-2xl shadow-lg overflow-hidden hover:-translate-y-1 hover:shadow-2xl transition-all " v-if="visibleCount < tCoffee.length"@click="showMore">
            Show More
        </button>
        <ul class="grid grid-cols-4 justify-center gap-8 p-6">
            <li class="bg-amber-50 border border-amber-200 rounded-2xl shadow-lg overflow-hidden hover:-translate-y-1 hover:shadow-2xl transition-all" 
            v-for="(cafe, index) in visibleCoffee" :key="index" >
                <h3 class="mr-14 text-amber-900 font-bold shadow-amber-950">{{ cafe.name }}</h3>
                <img class="w-full h-52 object-cover" :src="cafe.img" :alt="cafe.name">
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'Grid',
    props:["tCoffee"],
    data(){
        return{
            visibleCount: 1,
            visibleCoffee: [],
        }
    },
    mounted() {
    this.visibleCoffee = this.tCoffee.slice(0, this.visibleCount)
    },
    methods:{
        showMore(){
            if (this.visibleCount < this.tCoffee.length){
                this.visibleCount++;
                this.visibleCoffee = this.tCoffee.slice(0, this.visibleCount);
            }
        }
    }
}
</script>
