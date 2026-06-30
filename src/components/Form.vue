<template >
    <div>
        <form class="grid grid-rows-2 justify-center mt-11 gap-6 p-6">
    <label
      class="text-amber-900 font-black shadow-amber-950 mr-2"
      for="addName">
    New Coffee
      <input
        class="ml-12 bg-amber-50 border border-amber-200 rounded-2xl shadow-lg overflow-hidden hover:-translate-y-1 hover:shadow-2xl transition-all"
        v-model="newCoffee.name"
        id="addName"
        type="text"/>
    </label>
    <label class="text-amber-900 font-black shadow-amber-950 mr-3" for="addImg">
      New Image
      <input
        class="ml-6 bg-amber-50 border border-amber-200 rounded-2xl shadow-lg overflow-hidden hover:-translate-y-1 hover:shadow-2xl transition-all"
        v-model="newCoffee.img"
        id="addImg"
        type="url"
      />
    </label>
    <div class="flex justify-center mt-11">
      <button
        class="text-amber-900 font-bold shadow-amber-950 bg-amber-50 border border-amber-200 rounded-2xl shadow-lg overflow-hidden hover:-translate-y-1 hover:shadow-2xl transition-all"
        @click.prevent="addCoffee"
      >
        Add New Cofffee
      </button>
    </div>
  </form>
        
    </div>
</template>
<script>
export default {
    name : 'Form',
    data(){
        return{
            
            newCoffee: {
                    name: "",
                    img: "",
            },
        }
    },
    methods: {
        addCoffee() {
            this.$emit('aCoffee',this.newCoffee); 
            this.newCoffee = {name : "", img : ""};  
        }
    }
}
</script>