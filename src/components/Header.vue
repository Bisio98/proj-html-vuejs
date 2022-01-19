<template>
  <section>
    <div class="container">
      <div class="img_box">
        <img src="../assets/img/MasterStudy-1.svg" alt="" />
      </div>
      <div>
        <div v-for="(element, index) in headerLinks" :key="index">
          <h3
            @click="changeActive(index)"
            v-if="element.elementName !== 'Socials'"
          >
            {{ element.elementName }}
            <div class="selector" v-if="element.elementActive">
              <div class="line">
                <i class="fas fa-caret-up"></i>
              </div>
            </div>
            <span v-if="element.elementNew">NEW</span>
          </h3>
          <div class="link_socials" v-else>
            <i class="fab fa-linkedin"></i>
            <i class="fab fa-instagram"></i>
            <i class="fab fa-facebook"></i>
            <i class="fab fa-twitter"></i>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "Header",
  data: function () {
    return {
      headerLinks: [
        {
          elementName: "Courses",
          elementNew: false,
          elementActive: false,
        },
        {
          elementName: "Course Formats",
          elementNew: false,
          elementActive: false,
        },
        {
          elementName: "Add Course",
          elementNew: true,
          elementActive: false,
        },
        {
          elementName: "Pages",
          elementNew: false,
          elementActive: false,
        },
        {
          elementName: "Demos",
          elementNew: false,
          elementActive: true,
        },
        {
          elementName: "Socials",
          elementNew: false,
          elementActive: false,
        },
      ],
    };
  },
  methods: {
    changeActive: function (index) {
      for (let i = 0; i < this.headerLinks.length; i++) {
        this.headerLinks[i].elementActive = false;
      }
      this.headerLinks[index].elementActive = true;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
section {
  position: fixed;
  margin: auto;
  width: 100%;
  z-index: 2;
  overflow: hidden;
  background-color: white;

  .container {
    height: 150px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-around;
    margin: auto;

    .img_box {
      width: 30%;
    }

    img {
      height: 35px;
    }

    div {
      display: inline-block;

      h3 {
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;
        cursor: pointer;
        padding: 5px 25px;
        margin: 0 10px;

        span {
          background-color: red;
          padding: 3px 5px;
          color: white;
          position: absolute;
          font-size: 10px;
          border-top-left-radius: 4px;
          border-top-right-radius: 4px;
          border-bottom-right-radius: 4px;
          top: -15px;
          right: 0px;
        }

        .selector {
          .line {
            position: relative;
            width: 50px;
            height: 3px;
            background-color: #f2b71d;
          }

          i {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -70%);
            color: #f2b71d;
          }
        }
      }

      .link_socials {
        margin-left: 20px;

        i {
          margin: 0px 5px;
          cursor: pointer;
        }
      }
    }
  }
}
</style>
