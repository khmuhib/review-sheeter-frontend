<template>
  <div class="sticky-top shadow">
    <AppheaderTop></AppheaderTop>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <!-- <b-navbar-brand to="/">NavBar</b-navbar-brand> -->

      <div class="container ">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item to="/">Home</b-nav-item>
            <b-nav-item to="/about">About</b-nav-item>
            <b-nav-item-dropdown text="Serevices" right>
              <b-dropdown-item to="/webdesign">Web design</b-dropdown-item>
              <b-dropdown-item to="/b2b">B2B Lead Generation</b-dropdown-item>
              <b-dropdown-item to="amazonppc">Amazon PPC Service</b-dropdown-item>
            </b-nav-item-dropdown>
            <b-nav-item to="/contact">Contact</b-nav-item>
            <b-nav-item to="/blog">Blog</b-nav-item>
            <b-nav-item to="/dashboard" v-if="!loggedIn">Deshboard</b-nav-item>
            <b-nav-item href="#" disabled>Start Selling</b-nav-item>
            <b-nav-item href="#" disabled>Hire Us</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
              <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
              <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
            </b-nav-form>

            <b-nav-item-dropdown text="Lang" right>
              <b-dropdown-item href="#">EN</b-dropdown-item>
              <b-dropdown-item href="#">ES</b-dropdown-item>
              <b-dropdown-item href="#">RU</b-dropdown-item>
              <b-dropdown-item href="#">FA</b-dropdown-item>
            </b-nav-item-dropdown>

            <b-nav-item-dropdown right>
              <!-- Using 'button-content' slot -->
              <template #button-content>
                <em>User</em>
              </template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Sign Out</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </div>
    </b-navbar>
  </div>
</template>

<script>
import AppheaderTop from './AppheaderTop.vue';
export default {
  name: "AppHeader",
  components: { AppheaderTop },
  computed: {
    loggedIn() {
      return this.$store.state.auth.loggedIn;
    },

  }
};
</script>

<style scoped>
.logo-img {
  width: 160px;
}
</style>
