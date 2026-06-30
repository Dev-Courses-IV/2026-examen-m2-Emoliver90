<template>
  <div>
    <div class="flex justify-center" v-if="loading">
        </div>
        <div v-if="error">
        </div>
    <Grid :tCoffee ="tiposDeCafe"/>
    <Form @aCoffee ="apendCoffee"/>
  </div>
</template>
<script>
import Form from './components/Form.vue';
import Grid from './components/Grid.vue';
import Error from './components/Error.vue';
import Loading from './components/Loading.vue'

export default {
  name: 'App',
  components: {Grid,Form,Error,Loading},
  data(){
    return{
      loading:false,
      tiposDeCafe: [
                {
                    name: "Latte Macchiatto",
                    img: "https://www.shutterstock.com/image-photo/tasty-latte-macchiato-glasses-coffee-260nw-2600908089.jpg",
                },
                {
                    name: "White coffe",
                    img: "https://media.istockphoto.com/id/2173829000/es/foto/caf%C3%A9-latte-caliente-con-un-hermoso-arte-latte-servido-en-taza-de-color-verde.jpg?s=612x612&w=0&k=20&c=vGMqyzjXpScgvSvqIEge4E2V38F4D10KYRv4a2ku2IY=",
                },
                {
                    name: "Capuccino",
                    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQQOcle0BTcLNvYjIQR9aQOeBdcI1iZNz6uOA&s",
                },
                {
                    name: "MatchaLatte",
                    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR9svgCim1uNVbzpTD6uE8bLxtVlPDtf8bYuQ&s",
                },
            ],
    }
    
  },
  methods: {
    apendCoffee(newCoffee) {
      this.loading = true
            this.tiposDeCafe.push(newCoffee);
    },
  },
}
</script>
