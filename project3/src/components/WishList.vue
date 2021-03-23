<template>
<div class="wrapper">
  <div class="foods">
    <h2 v-if="this.$root.$data.items.length === 0">[The List is Empty]</h2>
    <div class="food" v-for="food in items" :key="food.id">
      <div class="info">
        <h1>{{food.name}}</h1>
      </div>
      <div class="image">
        <img :src="'/images/'+ food.image">
      </div>
      <div class="calories">
        <p>[{{food.calories}}]</p>
        <button class="auto" v-on:click="removeFromList(food)">Remove</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'WishList',
  props: {
    items: Array,
    foods: Array
  },
  methods: {
    removeFromList(food) {
        this.$root.$data.items.splice(this.$root.$data.items.indexOf(food), 1);
    }
  }, 
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.foods {
  display: flex;
  flex-flow: row wrap;
  flex-wrap: wrap;
  justify-content: space-around;
}

.food {
  margin: 1px;
  margin-top: 2em;
  width: 10em;
}

.food img {
  border: 2px solid rgb(163, 122, 122);
  height: 12em;
  width: 10em;
  object-fit: cover;
}

.food .image {
  display: flex;
  justify-content: center;
  
}

.info {
  background: #746666;
  margin-bottom: 2px;
  color: rgb(250, 246, 246);
  padding: 10px 30px;
  height: 3em;
  width: 10em;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.calories {
  display: flex;
  justify-content: space-between;
}

.calories p{
  font-size: .9em;
}

button {
  height: 2em;
  width: 5.5em;
  background: #756a6a;
  color: white;
  border: none;
  
}

button:hover {
  background: #414040;
}

.auto {
  margin-left: auto;
}
</style>