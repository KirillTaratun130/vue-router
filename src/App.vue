<template>
  <div class="wrapper">
    <header>
      <div class="navbar">
        <div class="container">
          <div class="navbar-content">
            <div class="logo">VueCLI</div>
            <ul class="navbar-list">
              <li class="navbar-item" v-for="link in links" :key="link.title">
                <router-link class="navbar-link" :title="link.title" :to="link.url">{{ link.title }}</router-link>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </header>


    <router-view></router-view>
  </div>
</template>

<script>


export default {
  name: 'Router',
  components: {},
  data() {
    return {
      links: [
        {
          title: 'Home',
          url: '/'
        },
        {
          title: 'Example',
          url: '/example'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.wrapper {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 99;
  padding: 20px 0;
  background-color: #ffffff;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
  &.logo {
    font-size: 24px;
  }
  .logo {
    margin-left: 50px;
  }
}

.navbar-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.navbar-list {
  display: flex;
  align-items: center;
  justify-content: center;
}

.navbar-item {
  padding-right: 50px;
  &:last-child {
    margin-right: 0;
  }
}

.navbar-link {
  display: block;
  color: #aaaad5;
  &.router-link-exact-active {
    color: red;
  }
}

li {
  list-style-type: none;
}

a {
  text-decoration: none;
}


</style>
