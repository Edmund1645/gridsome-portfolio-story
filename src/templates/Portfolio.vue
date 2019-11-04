<template>
  <Layout>
    <div class="work-container">
      <aside class="sidebar">
        <h3 class="no-space-top">{{$page.work.title}}</h3>
        <p>{{$page.work.description}}</p>
        <hr />
        <p>
          <strong class="work-details">Year</strong>
          {{$page.work.date}}
        </p>
        <p>
          <strong class="work-details">Client</strong>
          {{$page.work.client}}
        </p>
        <p>
          <strong class="work-details">Role</strong>
          {{$page.work.client}}
        </p>
        <p>
          <strong class="work-details">Link</strong>
          {{$page.work.link}}
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
strong.work-details {
  padding-right: auto;
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