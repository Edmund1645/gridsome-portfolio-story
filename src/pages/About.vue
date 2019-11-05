<template>
  <Layout>
    <div class="about">
      <div class="about__text">
        <h1>About Me</h1>
        <p>Pooping rainbow while flying in a toasted bread costume in space chase ball of string chew foot, and poop on grasses. Why must they do that flop over. Favor packaging over toy sleep nap and knock over christmas tree spread kitty litter all over house sweet beast. Use lap as chair give attitude poop on grasses sleep nap. Vommit food and eat it again purr while eating yet meowing non stop for food shove bum in owner's face like camera lens. Intently stare at the same spot stand in front of the computer screen purr for no reason stare at the wall, play with food and get confused by dust so present belly, scratch hand when stroked. Intrigued by the shower have secret plans. Sweet beast find something else more interesting, or stare at ceiling. Leave dead animals as gifts find something else more interesting. Lick butt. Sleep in the bathroom sink why must they do that. Intently sniff hand lick butt, and chase mice play time, but sweet beast, so cat snacks.</p>
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
  &__text {
    text-align: left;
  }
}
@media screen and (min-width: 768px) {
  .about {
    display: flex;
    flex-wrap: wrap;
    &__text {
      margin-right: 30px;
      max-width: 350px;
    }
  }
}
@media screen and (min-width: 1024px) {
  .about__text {
    margin-right: 50px;
    max-width: 600px;
  }
}
</style>

