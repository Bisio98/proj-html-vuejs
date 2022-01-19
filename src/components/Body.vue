<template>
  <section>
    <Jumbotron />
    <Signature />
    <Courses />
    <Order />
    <Why />
    <Numbers />
    <Comment />
  </section>
</template>

<script>
import Comment from "./Comment.vue";
import Courses from "./Courses.vue";
import Jumbotron from "./Jumbotron.vue";
import Numbers from "./Numbers.vue";
import Order from "./Order.vue";
import Signature from "./Signature.vue";
import Why from "./Why.vue";

export default {
  name: "Body",
  components: {
    Jumbotron,
    Signature,
    Courses,
    Order,
    Why,
    Numbers,
    Comment,
  },
};
</script>

<style lang="scss" scoped></style>
