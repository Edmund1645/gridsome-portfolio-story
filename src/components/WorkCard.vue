<template>
  <div class="work-card">
    <div class="work-card-details-container" :style="{backgroundImage: `url(${work.cover_image})`}">
      <div class="work-card-details">
        <h2 class="work-card-title" v-html="work.title"></h2>
        <small v-html="work.date"></small>

        <WorkTags :work="work" v-if="work.tags" />
      </div>

      <g-link class="work-card-link" :to="work.path">Link</g-link>
    </div>
  </div>
</template>

<script>
import WorkTags from './WorkTags.vue';
export default {
  components: {
    WorkTags
  },
  props: ['work']
};
</script>


<style lang="scss">
.work-card {
  width: 290px;
  height: 310px;
  border-radius: 10px;
  background-color: var(--bg-content-color);
  overflow: hidden;

  &-details-container {
    padding: 1rem;
    height: 100%;
    transition: transform 0.3s;
    position: relative;

    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #0f0f0f98;
    }
  }

  &-details {
    position: absolute;
    width: 100%;
    height: 100%;
  }

  &-title {
    margin-top: 0;
  }

  &:hover &-details-container {
    transform: scale(1.07);
    transition: transform 0.3s;
  }

  &-link {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    text-indent: -9999px;
    z-index: 0;
    opacity: 0;
  }
}
</style>
