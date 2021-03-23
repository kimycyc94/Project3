<template>
  <div>
    <h1>Your wish-to-eat list</h1>
    <WishList :items="items" />
  </div>
</template>

<script>
import WishList from "../components/WishList.vue"
export default {
  name: 'List',
  components: {
    WishList
  },
  data() {
    return {
    }
  },
  computed: {
    items() {
      return this.$root.$data.items;
    }
  },
  methods: {
  }
}
</script>

<style scoped>
h1 {
  margin-top: 15px;
  margin-bottom: 15px;
  font-weight: bold;
}
</style>
