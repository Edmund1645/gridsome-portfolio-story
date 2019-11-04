<template>
  <Layout>
    <div class="work-cards">
      <WorkCard v-for="edge in $page.portfolio.edges" :key="edge.node.id" :work="edge.node" />
    </div>
  </Layout>
</template>

<page-query>
query{
  portfolio: allPortfolio( filter: {published: {eq: true}}, sortBy: "date"){
    edges{
      node{
        id
        title
        path
        cover_image
        date(format: "D. MMMM YYYY")
        tags{
          id
          title
          path
        }
      }
    }
  }
}

</page-query>

<script>
import WorkCard from '~/components/WorkCard.vue';
export default {
  components: {
    WorkCard
  },
  metaInfo: {
    title: 'Work'
  }
};
</script>

<style>
</style>
