<template>
  <main class="background">
    <div class="container divide">
      <div class="left">
        <h3>Get My Exclusive Investing Book just for ${{ price }}</h3>
        <span
          >Vestibulum imentum eu urna vel cursus. Aenean vehicula quam quam,
          vitae pellentesque urna elementu, cursus.</span
        >
        <div class="img_box">
          <img src="../assets/img/amazon.png" alt="amazon link" />
        </div>
      </div>
      <div class="right">
        <img src="../assets/img/book.png" alt="" />
      </div>
    </div>
    <div class="commands">
      <img class="font_awesome" src="../assets/img/desktop-solid.svg" alt="" />
      <img
        class="font_awesome"
        src="../assets/img/life-ring-regular.svg"
        alt=""
      />
      <img class="font_awesome" src="../assets/img/wrench-solid.svg" alt="" />
      <img
        class="font_awesome"
        src="../assets/img/shopping-cart-solid.svg"
        alt=""
      />
      <img
        class="font_awesome"
        src="../assets/img/mobile-alt-solid.svg"
        alt=""
      />
    </div>
  </main>
</template>

<script>
export default {
  name: "Order",
  data: function () {
    return {
      price: 19.5,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";
main {
  background-image: url("../assets/img/slider_1-1917x607-1914x606.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  height: 70vh;
  position: relative;

  .divide {
    display: flex;
    justify-content: center;
    align-items: center;

    .left {
      h3 {
        font-size: 35px;
        color: #f2b71d;
      }

      span {
        display: inline-block;
        color: white;
        font-size: 20px;
        margin: 30px 0;
      }

      .img_box {
        width: 150px;
        margin: 20px auto;
        cursor: pointer;
      }
    }

    .right {
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      height: 70vh;
      justify-content: flex-end;

      img {
        width: 600px;
      }
    }

    .left,
    .right {
      width: 40%;
    }
  }

  .commands {
    position: absolute;
    display: flex;
    flex-direction: column;
    right: 0;
    top: 80px;
    width: 50px;
    height: 300px;
    background-color: white;
    align-items: center;
    justify-content: space-evenly;

    img {
      cursor: pointer;
    }
  }
}
</style>
