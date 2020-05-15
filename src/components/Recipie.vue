<template>
  <div class="root">
    <div class="container" v-bind:key="recipie.id" v-for="recipie in data">
        <h3>{{recipie.title}}</h3>
        <p><strong>Ingredients:</strong></p>
        <ul v-bind:key="ingredient.id" v-for="ingredient in recipie.ingredients">
            <li>{{ingredient.item}}</li>
         </ul>
        <img v-bind:src="recipie.thumbnail">
        <p>attribute: <a v-bind:href="recipie.href"/>{{recipie.href}}</p>
    </div>
  </div>
</template>

<script>


export default {
    name: 'Recipie',
    props: ["data"],
    created() {

    },
};

</script>

<style scoped>
    .root {
        display: flex;
        flex-flow: column;
        background-color: lightgray;
    }
    .container {
        border: 1px solid black;
        margin: 5px 15px;
        background-color: white;        
        padding: 30px;
    }
    h3, img, p {
        margin: 5px 0;
    }
    ul {
        padding-left: 20px;
    }
</style>
