<template>
    <div class="menu-bar">
        <div class="buttons">
            <div class = "button">
                <a @click="select('American')" href="#"><b-button pill variant="primary">American Cuisine</b-button></a>
            </div>
            <div class = "button">
                <a @click="select('Korean')" href="#"><b-button pill variant="secondary">Korean Cuisine</b-button></a>
            </div>
            <div class = "button">
                <a @click="select('Mexican')" href="#"><b-button pill variant="success">Mexican Cuisine</b-button></a>
            </div>
            <div class = "button">
                <a @click="select('Japanese')" href="#"><b-button pill variant="danger">Japanese Cuisine</b-button></a>
            </div>
        </div>
        <br>
        <h4>Selected:</h4>
        <div>
            <FoodList :foods="foods" />
        </div>
    </div>
</template>

<script>
// @ is an alias to /src

import FoodList from "../components/FoodList.vue"
export default {
  name: 'Cuisine',
  components: {
    FoodList
  },
  data() {
    return {
      country: '',
    }
  },
  computed: {
    foods() {
      return this.$root.$data.foods.filter(food => food.country === this.country);
    }
  },
  methods: {
    select(country) {
      this.country = country;
    }
  }
}
</script>


<style>
    .menu-bar {
        display: flex;
        flex-flow: column;
        margin-top: 20px;
    }

    b-form-group label {
        font-size: 2em;
    }

    .buttons {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
        align-items: center;
    }

    .button {
        margin-bottom: 1em;
    }
</style>