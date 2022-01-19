<template>
  <main>
    <div class="image_box">
      <img class="toHover" v-bind:src="requireImg(element.img)" alt="" />
      <span class="special" v-if="element.special">SPECIAL</span>
      <span class="price">{{ element.price }}</span>
    </div>
    <div class="description">
      <div class="top">
        <h3>{{ element.name }}</h3>
        <h5>{{ element.category }}</h5>
      </div>
      <div class="line"></div>
      <div class="extras">
        <div class="symbols">
          <img
            class="font_awesome"
            src="../assets/img/signal-solid.svg"
            alt=""
          />
          {{ element.difficulty }}
        </div>

        <div class="symbols">
          <img
            class="font_awesome"
            src="../assets/img/list-ul-solid.svg"
            alt=""
          />
          {{ element.length }}
        </div>

        <div class="symbols">
          <img
            class="font_awesome"
            src="../assets/img/clock-regular.svg"
            alt=""
          />
          {{ element.hours }}
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "SingleCourse",
  props: {
    element: Object,
  },

  methods: {
    requireImg: function (pic) {
      return require("../assets/img/" + pic);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";

main {
  width: calc(100% / 4);
  border: 1px solid #bcbcbc;
  margin: 20px 30px;

  .image_box {
    position: relative;
    z-index: 1;

    &:hover img {
      filter: brightness(20%);
    }

    &:hover .price {
      display: inline-block;
    }

    .price {
      position: absolute;
      top: 50%;
      left: 50%;
      color: white;
      font-size: 20px;
      transform: translate(-50%, -50%);
      display: none;
    }

    .special {
      position: absolute;
      top: 10px;
      right: 10px;
      color: white;
      background-color: #f2b71d;
      padding: 5px;
      border-radius: 10px;
    }
  }

  .description {
    .top {
      margin: 40px 0;
      text-align: center;

      h3 {
        font-size: 25px;
      }

      h5 {
        color: #bcbcbc;
        margin: 10px 0;
      }
    }

    .line {
      width: 90%;
      height: 2px;
      background-color: #bcbcbc;
      margin: 10px auto;
    }

    .extras {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      padding: 30px 0;

      .symbols {
        img {
          margin: 0px 5px;
        }
      }
    }
  }
}
</style>
