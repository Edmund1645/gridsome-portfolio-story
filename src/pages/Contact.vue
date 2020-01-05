<template>
  <Layout>
    <div class="layout">
      <h2 class="bottom-line">Looking to get in touch?</h2>
      <p>
        If you would like to inquire about a new project, speaking engagements, chat about product design or just say a friendly hello, please feel free to reach via
        <a
          class="email-link"
          href="mailto:example@gmail.com"
        >email</a>.
      </p>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Contact Me'
  }
};
</script>

<style lang="scss"scoped>
h2 {
  margin-bottom: 2rem;
}
.bottom-line {
  position: relative;
}
.bottom-line::after {
  content: '';
  height: 3px;
  width: 80px;
  background: var(--accent-color);
  position: absolute;
  bottom: -10px;
  left: 0;
}
.email-link {
  text-decoration: underline;
}
</style>