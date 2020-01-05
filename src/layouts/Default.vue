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
          <g-link class="nav__link" to="/contact/">Contact</g-link>
        </nav>
      </div>
    </header>
    <div class="wrapper">
      <div class="layout">
        <slot />
      </div>
    </div>
    <footer class="footer">
      <div class="footer__content">
        <p>
          Built with 🍻 by
          <a target="_blank" href="//edmundekott.me">Edmund Ekott</a>
        </p>
        <p>
          Powered by
          <a target="_blank" href="//gridsome.org">Gridsome</a>
        </p>
      </div>
    </footer>
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
  min-height: 80vh;
  padding-top: 40px;
}
.layout {
  max-width: 960px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  padding-bottom: 30px;
}
.header {
  background: var(--bg-header);
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

.footer {
  background: var(--bg-footer);
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;

  p {
    a {
      color: currentColor;
      text-decoration: underline;
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
    z-index: 1000;
  }
}
@media screen and (min-width: 1024px) {
  .layout,
  .navigation-bar {
    max-width: 1000px;
  }
}
</style>
