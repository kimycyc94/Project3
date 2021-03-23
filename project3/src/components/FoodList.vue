<template>
<div class="wrapper">
  <div class="foods">
    <div class="food" v-for="food in foods" :key="food.id">
      <div class="info">
        <h1>{{food.name}}</h1>
      </div>
      <div class="image">
        <img :src="'/images/'+ food.image">
      </div>
      <div class="calories">
        <p>[{{food.calories}}]</p>
        <button class="auto" onclick="alert('The item is added to your wish lsit');" v-on:click="addToList(food)">Add to List</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'FoodtList',
  props: {
    foods: Array,
    //items: Array,
  },
  methods: {
    addToList(food) {
      let exist = false;
      if (this.$root.$data.items) {
        this.$root.$data.items.forEach(item => {
          if (item.id == food.id) {
            exist = true;
          } 
        });
      }
      if (!exist) {
        this.$root.$data.items.push(food);
      }
    }
  }
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
  border: 2px solid rgb(187, 11, 11);
  height: 12em;
  width: 10em;
  object-fit: cover;
}

.food .image {
  display: flex;
  justify-content: center;
  
}

.info {
  background: #d81d1d;
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
  background: #d81d1d;;
  color: white;
  border: none;
  
}

button:hover {
  background: rgb(247, 78, 78);
}

.auto {
  margin-left: auto;
}
</style>