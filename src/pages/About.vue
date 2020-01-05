<template>
  <Layout>
    <div class="about">
      <div class="about-text">
        <h1>About Me</h1>
        <p>They don’t want us to eat. You see that bamboo behind me though, you see that bamboo? Ain’t nothin’ like bamboo. Bless up. Egg whites, turkey sausage, wheat toast, water. Of course they don’t want us to eat our breakfast, so we are going to enjoy our breakfast. Mogul talk. They will try to close the door on you, just open it. You smart, you loyal, you a genius. Special cloth alert. Surround yourself with angels, positive energy, beautiful people, beautiful souls, clean heart, angel. Another one. You see the hedges, how I got it shaped up? It’s important to shape up your hedges, it’s like getting a haircut, stay fresh.</p>
      </div>
      <div class="about-photo">
        <g-image src="~/assets/images/person.jpg" width="300" />
      </div>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'About Me'
  }
};
</script>

<style lang="scss" scoped>
.about {
  &-text {
    text-align: left;
  }
}
@media screen and (min-width: 768px) {
  .about {
    display: flex;
    flex-wrap: wrap;
    &-text {
      margin-right: 30px;
      max-width: 350px;
    }
  }
}
@media screen and (min-width: 1024px) {
  .about-text {
    margin-right: 50px;
    max-width: 600px;
  }
}
</style>

