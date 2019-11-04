<template>
  <div>
    <header class="header">
      <div class="navigation-bar">
        <strong>
          <g-link to="/">{{ $static.metadata.siteName }}</g-link>
        </strong>
        <nav v-if="showNav" class="nav">
          <g-link class="nav__link" to="/">Work</g-link>
          <g-link class="nav__link" to="/about/">About</g-link>
        </nav>
      </div>
    </header>
    <div class="wrapper">
      <div class="layout">
        <slot />
      </div>
    </div>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
  props: {
    showNav: {
      default: true
    }
  }
};
</script>


<style lang='scss'>
.wrapper {
  background-color: var(--bg-color);
  min-height: 100vh;
  padding-top: 100px;
}
.layout {
  max-width: 960px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  padding-bottom: 30px;
}
.header {
  background: var(--bg-content-color);
}
.navigation-bar {
  max-width: 960px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;

  a {
    color: #ffffff;
  }

  .nav {
    .active--exact {
      color: var(--link-color);
    }

    &__link {
      margin-left: 20px;

      &:hover {
        color: var(--link-color);
      }
    }
  }
}
@media screen and (max-width: 650px) {
  .header {
    height: 65px;
  }
}
@media screen and (min-width: 760px) {
  .header {
    position: sticky;
    top: 0px;
    z-index: 10;
  }
}
@media screen and (min-width: 1024px) {
  .layout,
  .navigation-bar {
    max-width: 1000px;
  }
}
</style>
