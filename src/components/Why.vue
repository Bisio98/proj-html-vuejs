<template>
  <section class="container_60">
    <div class="title">
      <h3>Why my Courses?</h3>
    </div>
    <div class="card_container">
      <SingleCard
        v-for="(cardInfo, index) in slides"
        :key="index"
        :element="cardInfo"
      />
    </div>
  </section>
</template>

<script>
import SingleCard from "./SingleCard.vue";

export default {
  name: "Why",
  components: {
    SingleCard,
  },
  data: function () {
    return {
      slides: [
        {
          name: "Entrepreneurship",
          text: "Vestibulum vitae aliquam nunc. Suspendisse mollis metus ac tellus egestas pharetra. Suspendisse at viverra purus. Pellentesque nec posuere ligula, eu congue leo. Integer vulputate tempor arcu. Vestibulum vuplutate",
          img: "work",
        },
        {
          name: "Accellerated Learning",
          text: "Vestibulum vitae aliquam nunc. Suspendisse mollis metus ac tellus egestas pharetra. Suspendisse at viverra purus. Pellentesque nec posuere ligula, eu congue leo. Integer vulputate tempor arcu. Vestibulum vuplutate",
          img: "space",
        },
        {
          name: "Productivity",
          text: "Vestibulum vitae aliquam nunc. Suspendisse mollis metus ac tellus egestas pharetra. Suspendisse at viverra purus. Pellentesque nec posuere ligula, eu congue leo. Integer vulputate tempor arcu. Vestibulum vuplutate",
          img: "thumb",
        },
        {
          name: "Life Coaching",
          text: "Vestibulum vitae aliquam nunc. Suspendisse mollis metus ac tellus egestas pharetra. Suspendisse at viverra purus. Pellentesque nec posuere ligula, eu congue leo. Integer vulputate tempor arcu. Vestibulum vuplutate",
          img: "gear",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";
section {
  .title {
    text-align: center;
    margin: 50px 0;
    font-size: 35px;
  }

  .card_container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
  }
}
</style>
