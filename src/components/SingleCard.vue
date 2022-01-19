<template>
  <section>
    <div class="left">
      <img
        v-if="element.img === 'work'"
        class="font_awesome"
        src="../assets/img/briefcase-solid.svg"
        alt=""
      />
      <img
        v-else-if="element.img === 'space'"
        class="font_awesome"
        src="../assets/img/rocket-solid.svg"
        alt=""
      />
      <img
        v-else-if="element.img === 'thumb'"
        class="font_awesome"
        src="../assets/img/thumbs-up-solid.svg"
        alt=""
      />
      <img
        v-else
        class="font_awesome"
        src="../assets/img/cog-solid.svg"
        alt=""
      />
    </div>
    <div class="right">
      <h3>{{ element.name }}</h3>
      <span>{{ element.text }}</span>
    </div>
  </section>
</template>

<script>
export default {
  name: "SingleCard",
  props: {
    element: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";
section {
  border: 1px solid #e4e7e7;
  border-left: 4px solid #f2b71d;
  width: 40%;
  margin: 30px 20px;
  display: flex;

  .left {
    width: 20%;

    img {
      height: 60px;
      width: 60px;
      margin: 20px 15px;
    }
  }

  .right {
    width: 80%;

    h3 {
      font-size: 25px;
      margin: 20px 5px;
    }

    span {
      line-height: 25px;
      display: inline-block;
      margin: 20px 5px;
    }
  }

  &:hover {
    background-color: #f2b71d;
  }
}
</style>
