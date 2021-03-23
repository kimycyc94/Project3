<template>
  <div class="home_body">
    <div class="slide_image">
      <b-carousel
        id="carousel-1"
        v-model="slide"
        :interval="4000"
        controls
        indicators
        background="#ababab"
        img-width="50px"
        img-height="480"
        style="text-shadow: 1px 1px 2px #333;"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
      <!-- Text slides with image -->
      <b-carousel-slide
        caption="What should I eat today?"
        text="If you are having a hard time to decide, welcome!"
        img-src="/images/home1.jpg" 
      ></b-carousel-slide>

      <!-- Text slides with image -->
      <b-carousel-slide
        caption="Food recommendation"
        text="We have many food options for you!"
        img-src="/images/home2.jpg"
      ></b-carousel-slide>

      <!-- Text slides with image -->
      <b-carousel-slide
        caption="Diversity is important"
        text="Foods from Korea, America, Mexico, and Japan"
        img-src="/images/home3.jpg"
      ></b-carousel-slide>

      <!-- Text slides with image -->
      <b-carousel-slide
        img-src="/images/home4.jpg"
      ></b-carousel-slide>
      </b-carousel>
    </div>
    <div>
      <hr>
      <h2>Recommendation</h2>
      <FoodList :foods="foods" />
    </div>
  </div>

</template>


<script>
// @ is an alias to /src
import FoodList from "../components/FoodList.vue"
export default {
  name: 'Home',
  components: {
    FoodList
  },
  data() {
    return {
      slide: 0,
      sliding: null
    }
  },
  computed: {
    foods() {
      return this.$root.$data.foods;
    },
  },
  methods: {
      /*onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      }*/
  }
}
</script>

<style>
  .home-logo {
    padding-top: 20px;
  }

  .home_body {
    padding-top: 20px;
    display: flex;
    flex-flow: column wrap;
    align-items: center;
    justify-content: center;
  }
  .slide_image {
    border: 2px solid rgb(90, 88, 88);
    width: 70%;
    height: auto;
    margin-bottom: 1em;
  }

.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>
