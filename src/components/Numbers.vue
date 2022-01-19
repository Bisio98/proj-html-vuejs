<template>
  <main class="background">
    <div class="elements_container container">
      <div
        class="element_container"
        v-for="(singleElement, index) in datas"
        :key="index"
      >
        <div class="left">
          <img
            v-if="singleElement.name === 'Online Learner'"
            class="font_awesome"
            src="../assets/img/user-friends-solid.svg"
            alt=""
          />
          <img
            v-else-if="singleElement.name === 'Video Curses'"
            class="font_awesome"
            src="../assets/img/film-solid.svg"
            alt=""
          />
          <img
            v-else-if="singleElement.name === 'Sliders & Images'"
            class="font_awesome"
            src="../assets/img/image-regular.svg"
            alt=""
          />
          <img
            v-else
            class="font_awesome"
            src="../assets/img/thumbs-up-solid.svg"
            alt=""
          />
        </div>
        <div class="right">
          <span class="numbers">{{ singleElement.num }}</span>
          {{ singleElement.name }}
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "Numbers",
  data: function () {
    return {
      datas: [
        {
          name: "Online Learner",
          num: 3195,
        },
        {
          name: "Video Curses",
          num: 23,
        },
        {
          name: "Sliders & Images",
          num: 437,
        },
        {
          name: "Excellent Reviews",
          num: 1440,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";
main {
  background-image: url("../assets/img/counter-1919x1101.jpg");
  color: white;
  background-size: cover;
  background-repeat: no-repeat;

  .elements_container {
    display: flex;
    justify-content: space-evenly;
    padding: 250px 0;

    .element_container {
      display: flex;
      align-items: center;

      .left {
        width: 40%;

        img {
          width: 50px;
          height: 50px;
        }
      }

      .right {
        display: flex;
        flex-direction: column;
        width: 60%;
        font-size: 20px;

        span {
          color: #f2b71d;
          font-size: 40px;
        }
      }
    }
  }
}
</style>
