<template>
  <div class="work-card">
    <!-- :style="{backgroundImage: `url(${work.cover_image})`}" -->
    <div class="work-card-details-container">
      <div class="work-card-header">
        <g-image alt="Cover Image" class="work-image" :src="work.cover_image" />
      </div>
      <div class="work-card-details">
        <h4 class="work-card-title" v-html="work.title"></h4>
        <small v-html="work.date"></small>
      </div>
      <WorkTags :work="work" v-if="work.tags" />

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
  width: 300px;
  height: 320px;
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
      z-index: 2;
    }
  }

  &-details {
    position: absolute;
    z-index: 3;
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
    z-index: 4;
    opacity: 0;
  }
}
.work-card-header {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 0;
  height: 170px;
  overflow: hidden;
}
.work-image {
  min-width: 100%;
}
@media screen and (max-width: 625px) {
  .work-card {
    width: 87%;
    margin-top: 30px;
  }
}
</style>
