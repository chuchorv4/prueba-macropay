<template>
  <b-navbar toggleable="lg" type="light" variant="light" sticky="true">
    <b-navbar-brand href="/">Macromedia</b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav v-for="option in menu.options" :key="option._id">
        <b-nav-item :href="option.url">{{ option.name }}</b-nav-item>
      </b-navbar-nav>

      <b-navbar-nav class="ml-auto">
        <b-nav-item href="#">
          <b-icon class="m-auto" icon="cart" font-scale="1"></b-icon>
        </b-nav-item>
        <b-nav-item-dropdown right>
          <template #button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>

    </b-collapse>
  </b-navbar>
</template>
<script>
export default {
  data() {
    return {
      menu: {
        options: [
          {
            _id: 0,
            name: 'Products',
            url: '/products'
          },
          {
            _id: 1,
            name: 'About',
            url: '/about'
          },
          {
            _id: 2,
            name: 'Contact',
            url: '/contact'
          },
        ]
      }
    }
  }
}
</script>