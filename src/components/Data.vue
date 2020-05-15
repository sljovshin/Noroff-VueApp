<template>
  <Recipie v-bind:data="data" />
</template>

<script>
import Recipie from './Recipie';
import axios from 'axios';


export default {
  name: 'Data',
  components: {
    Recipie,
  },
  data() {
    return {
      data: [
      
      ],
    }
  },
  beforeCreate () {    
      axios.get('https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api/')
           .then(res => this.data = this.listifyString(res.data.results))
           .catch(error => console.log(error));
  },
  methods: {
    listifyString(obj) {
        let ingredients = [];
        let id = 0;
        obj.forEach(item => {
            let list = item.ingredients.split(', ');
            list = list.map(entry => {return {item: entry, id: id++} })
            ingredients.push(list);
        });
        obj.forEach((item, index) => {
            item.ingredients = ingredients[index];
        })
        return obj;
    },
    

    
  }
}
</script>