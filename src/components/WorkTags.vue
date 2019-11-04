<template>
  <div class="work-tags">
    <g-link
      class="work-tags-link"
      v-for="tag in work.tags"
      :key="tag.id"
      :to="tag.path"
    >{{ tag.title}}</g-link>
  </div>
</template>

<script>
export default {
  props: ['work']
};
</script>

<style lang="scss">
.work-tags {
  margin: 1.5em 0 0;
  position: absolute;
  bottom: 60px;
  z-index: 20;

  &-link {
    margin-right: 1em;
    color: currentColor;
    background-color: var(--card-tag-bg);
    font-size: 0.7em;
    border-radius: 25em;
    padding: 0.05em 0.5em;
  }
}
</style>
