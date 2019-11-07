<template>
  <Layout :showNav="true">
    <h1>{{ $page.tag.title}}</h1>

    <div class="work-cards">
      <WorkCard v-for="edge in $page.tag.belongsTo.edges" :key="edge.node.id" :work="edge.node" />
    </div>
  </Layout>
</template>
<page-query>
query Tag ($id: ID!) {
  tag(id: $id) {
    title
    belongsTo (sortBy: "date") {
      edges {
        node {
          ... on Portfolio {
            id
            title
            path
            cover_image(width: 700, height: 400, blur: 7, fit:cover )
            date(format: "D. MMMM YYYY")
          }
        }
      }
    }
  }
}

</page-query>
<script>
import WorkCard from '~/components/WorkCard.vue';
export default {
  name: 'tag',
  components: {
    WorkCard
  },
  metaInfo() {
    return {
      title: this.$page.tag.title
    };
  }
};
</script>

<style>
</style>