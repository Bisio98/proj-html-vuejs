<template>
  <main>
    <div class="division container_60">
      <div class="left">
        <h4>
          Hey there, my name is John Doe. I'm the founder of the Brain Academy
        </h4>
        <div class="img_box">
          <img src="../assets/img/sign.jpg" alt="Signature" />
        </div>
      </div>
      <div class="right">
        <span
          >A wonderful serenity has taken possession of my entire soul, like
          these sweet mornings of spring which I enjoy with my whole heart. I am
          alone, and feel the charm of existence in this spot, which was created
          for the bliss of souls like mine. I am so happy, my dear friend, so
          absorbed in the exquisit sense of mere tranquil existence, that I
          neglet my talents. When, while the lovely valley teems with vapour
          around me, and the meridian sun strikes the upper surface of the
          impenetrable foliage of my trees, and but a few stray gleams steal
          into the inner sanctuary</span
        >
      </div>
    </div>
  </main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
@import "../style/general.scss";
main {
  padding-top: 200px;

  .division {
    display: flex;
    justify-content: space-evenly;

    .left {
      display: flex;
      flex-direction: column;
      align-items: center;

      h4 {
        font-size: 40px;
        margin-bottom: 15px;
      }

      .img_box {
        width: 200px;
        margin: 20px 0;
      }
    }

    .right {
      line-height: 25px;
    }

    .right,
    .left {
      width: 40%;
      padding: 15px;
      margin-bottom: 40px;
    }
  }
}
</style>
