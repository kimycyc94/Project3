<template>
  <b-navbar type="dark" variant="dark">
    <b-navbar-nav>
      <b-nav-item> <router-link to="/"> Home </router-link></b-nav-item>

      <!-- Navbar dropdowns -->
      <b-nav-item-dropdown text="Menu" right>
        <b-dropdown-item> <router-link to="/cuisine">By Cuisine</router-link></b-dropdown-item>
        <b-dropdown-item> <router-link to="/list">Wish List</router-link></b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar-nav>
  </b-navbar>
</template>


<script>
export default {
    name: "header",
};
</script>

<style>

</style>