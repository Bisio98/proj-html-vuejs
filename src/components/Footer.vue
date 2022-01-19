<template>
  <section>
    <div class="container">
      <div class="col" v-for="(elements, index) in footerData" :key="index">
        <h5>{{ elements.name }}</h5>
        <ul
          :class="{
            no_style: elements.name !== 'PAGES',
            list: elements.name === 'PAGES',
            img_bot: elements.name === 'BLOG',
          }"
        >
          <li v-for="(singleelement, ind) in elements.element" :key="ind">
            {{ singleelement.text }}
            <div class="socials" v-if="elements.name === 'ABOUT'">
              <i class="fab fa-facebook"></i>
              <i class="fab fa-twitter"></i>
              <i class="fab fa-instagram"></i>
            </div>
            <div class="image_block" v-else-if="elements.name === 'BLOG'">
              <img v-bind:src="requireImg(singleelement.image)" alt="" />
              <div>
                <span>{{ singleelement.description }}</span>
                <br />
                <span class="date">{{ singleelement.date }}</span>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Header",
  data: function () {
    return {
      footerData: [
        {
          name: "ABOUT",
          element: [
            {
              text: "Masterstudy is Education WordPress theme featured by Learning Management System (LMS) for online education. Developed by StylemixThemes",
            },
          ],
        },
        {
          name: "CONTACT",
          element: [
            {
              text: "USA, Callifornia 20, First avenue, Callifornia",
            },
            {
              text: "tel.:+1 212 458 300 32",
            },
            {
              text: "tel.:+1 212 675 24 14",
            },
            {
              text: "info@masterstudy.com",
            },
          ],
        },
        {
          name: "PAGES",
          element: [
            {
              text: "Blog",
            },
            {
              text: "Courses",
            },
            {
              text: "Home",
            },
            {
              text: "Membership Account",
            },
            {
              text: "Shortcodes",
            },
            {
              text: "Typography",
            },
          ],
        },
        {
          name: "BLOG",
          element: [
            {
              image: "photo-1517520287167-4bbf64a00d66-129x129.jpeg",
              description: `Our main target is to "Developing Yourself as a Leader"`,
              date: "-August 9, 2018",
            },
            {
              image: "photo-1490376840453-5f616fbebe5b-129x129.jpeg",
              description: `Those Other College Expenses You Aren't Thinking About`,
              date: "-June 3, 2015",
            },
          ],
        },
      ],
    };
  },
  methods: {
    ulStyle: function (i) {
      if (this.footerData[i] !== "PAGES") {
        return true;
      } else {
        return false;
      }
    },
    requireImg: function (pic) {
      return require("../assets/img/" + pic);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
section {
  padding-top: 50px;
  background-color: #f2b71d;
  width: 100%;

  .container {
    width: 100%;
    display: flex;
    justify-content: space-around;

    .col {
      width: 20%;
      padding: 50px;

      .socials {
        margin: 10px 0;

        i {
          cursor: pointer;
          margin: 0px 5px;
        }
      }

      .list {
        height: 100%;
        cursor: pointer;
        position: relative;
        left: 20px;

        li {
          width: 200px;
        }

        li:nth-child(2n) {
          position: relative;
          bottom: 30px;
          left: 200px;
        }
      }

      .image_block {
        display: flex;

        img {
          height: 100px;
          width: 100px;
          margin-right: 20px;
        }

        .date {
          font-size: 12px;
        }
      }

      li {
        margin: 10px 0;
      }

      h5 {
        font-size: 23px;
        margin: 10px 0;
      }

      .no_style {
        list-style: none;
      }
    }
  }
}
</style>
