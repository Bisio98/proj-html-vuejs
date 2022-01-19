<template>
  <section>
    <h3>What Students Say</h3>
    <div class="container_60">
      <div class="change_comment">
        <div class="top">
          <img
            @click="changeActiveSub"
            class="cursor font_awesome"
            src="../assets/img/arrow-left-solid.svg"
            alt=""
          />
          <div
            class="profile_pics"
            v-for="(element, index) in persons"
            :key="index"
          >
            <div class="image_box">
              <img
                @click="changeActive(index)"
                :class="{ big: element.visible }"
                :src="requireImg(element.img)"
                alt=""
              />
            </div>
          </div>
          <img
            @click="changeActiveAdd"
            class="cursor font_awesome"
            src="../assets/img/arrow-right-solid.svg"
            alt=""
          />
        </div>

        <div v-for="(element, index) in persons" :key="index">
          <div class="container_60">
            <div v-if="element.visible">
              <h5>{{ element.title }}</h5>
              <div class="stars">
                <img
                  v-for="(star, index) in element.stars"
                  :key="index"
                  class="font_awesome"
                  src="../assets/img/star-solid.svg"
                  alt=""
                />
                <img
                  v-for="(star, index) in 5 - element.stars"
                  :key="index"
                  class="font_awesome"
                  src="../assets/img/star-regular.svg"
                  alt=""
                />
              </div>
              <span>{{ element.text }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Comment.vue",
  data: function () {
    return {
      show: 1,
      persons: [
        {
          id: 0,
          visible: false,
          img: "1-100x100.jpg",
          stars: 3,
          title: "Paints of the Future 1",
          text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        },
        {
          id: 1,
          visible: true,
          img: "2-100x100.jpg",
          stars: 5,
          title: "Paints of the Future 2",
          text: 'The response to your MasterStudy has been really overwhelming! Those who partecipated in the workshop are spreading the world here on campus and the "buzz" is on. The VP of the Istruction wants you to come back! Her goal is to have more faculty trained. She also wants to attend a workshop herself. Our President told me Masterstudy needs to be the cornerstone of our success program',
        },
        {
          id: 2,
          visible: false,
          img: "3-100x100.jpg",
          stars: 4,
          title: "Paints of the Future 3",
          text: "Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur?",
        },
      ],
    };
  },
  methods: {
    requireImg: function (pic) {
      return require("../assets/img/" + pic);
    },
    changeActiveAdd: function () {
      for (let i = 0; i < this.persons.length; i++) {
        if (this.persons[i].visible === true && i !== this.persons.length - 1) {
          this.persons[i].visible = false;
          this.persons[i + 1].visible = true;
          this.show++;
          return;
        }
      }
    },
    changeActiveSub: function () {
      for (let i = 0; i < this.persons.length; i++) {
        if (this.persons[i].visible === true && i !== 0) {
          this.persons[i].visible = false;
          this.persons[i - 1].visible = true;
          this.show--;
          return;
        }
      }
    },
    changeActive: function (index) {
      for (let i = 0; i < this.persons.length; i++) {
        this.persons[i].visible = false;
      }
      this.persons[index].visible = true;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";
section {
  padding: 50px 0;
  text-align: center;

  .cursor {
    cursor: pointer;
  }

  .top {
    display: flex;
    justify-content: center;
    margin: 50px 0;

    .image_box {
      width: 150px;
      height: 150px;
      margin: 0px 20px;
      cursor: pointer;

      img {
        border-radius: 50%;
        width: 100px;
        height: 100px;
      }

      .big {
        height: 150px;
        width: 150px;
      }
    }
  }

  h5 {
    font-size: 30px;
    margin: 20px 0;
  }

  span {
    line-height: 30px;
    font-size: 20px;
  }

  .change_comment {
    display: flex;
    flex-direction: column;
  }

  .stars{
    display: flex;
    justify-content: center;

    img{
      margin: 0 5px 20px;
    }
  }
}
</style>
