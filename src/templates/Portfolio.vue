<template>
  <Layout>
    <div class="work-container">
      <aside class="sidebar">
        <h3 class="no-space-top">{{$page.work.title}}</h3>
        <p>{{$page.work.description}}</p>
        <hr />
        <p class="work-details">
          <strong>Year</strong>
          <span>{{$page.work.date}}</span>
        </p>
        <p class="work-details">
          <strong>Client</strong>
          <span>{{$page.work.client}}</span>
        </p>
        <p class="work-details">
          <strong>Role</strong>
          <span>{{$page.work.client}}</span>
        </p>
        <p class="work-details">
          <strong>Link</strong>
          <a :href="`//${$page.work.link}`" class="work-link" target="_blank">{{$page.work.link}}</a>
        </p>
      </aside>
      <article class="content">
        <div v-html="$page.work.content"></div>
      </article>
    </div>
  </Layout>
</template>

<page-query>
query Portfolio ($path: String!) {
  work: portfolio(path: $path) {
    id
    title
    description
    cover_image
    content
    path
    date (format: "YYYY")
    timeToRead
    client
    role
    link
  }
}
</page-query>
<script>
export default {
  metaInfo() {
    return {
      title: this.$page.work.title
    };
  }
};
</script>

<style lang="scss">
.sidebar {
  .work-details {
    display: table;
    table-layout: fixed;
    strong {
      width: 150px;
      display: table-cell;
    }

    & a.work-link {
      color: #ffffff;
    }
  }
}
@media screen and (min-width: 1024px) {
  .work-container {
    width: 100%;
    display: flex;
  }
  .sidebar {
    flex-basis: 35%;
    padding-right: 3rem;
  }
  .content {
    flex: 1;
  }
}
</style>