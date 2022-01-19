<template>
  <section>
    <div class="container">
      <h2>New Courses</h2>
      <div class="cards">
        <SingleCourse
          v-for="(course, index) in courses"
          :key="index"
          :element="course"
        />
      </div>
      <div class="bottom">
        <button>LOAD MORE</button>
      </div>
    </div>
  </section>
</template>

<script>
import SingleCourse from "./SingleCourse.vue";
export default {
  name: "Courses",
  components: {
    SingleCourse,
  },
  data: function () {
    return {
      courses: [
        {
          name: "How to be a DJ? Make Electronic Music",
          img: "photo-1496307042754-b4aa456c4a2d-740x400.jpeg",
          category: "Electronic",
          difficulty: "Advanced",
          length: "8 Lectures",
          hours: "6 hours",
          price: "129$",
          special: true,
        },
        {
          name: "Nvidia and UE$ Technologies Practice",
          img: "12345-1-740x400.png",
          category: "Nvidia",
          difficulty: "Advanced",
          length: "8 Lectures",
          hours: "6 hours",
          price: "159$",
          special: true,
        },
        {
          name: "Fashion Photography from professionals",
          img: "photo-1491897554428-130a60dd4757-740x400.jpeg",
          category: "Fashion",
          difficulty: "Advanced",
          length: "6 Lectures",
          hours: "6 hours",
          price: "99$",
          special: true,
        },
        {
          name: "Design Instrument for Communication",
          img: "photo-1416339134316-0e91dc9ded92-740x400.jpeg",
          category: "Communication",
          difficulty: "Intermediate",
          length: "6 Lectures",
          hours: "6 hours",
          price: "59$",
          special: false,
        },
        {
          name: "Make your Concept Right and Beautiful",
          img: "cathryn-lavery-67852-unsplash-740x400.jpg",
          category: "Art",
          difficulty: "Intermediate",
          length: "6 Lectures",
          hours: "6 hours",
          price: "59$",
          special: false,
        },
        {
          name: "Road Bike Manual or How to be a Champion",
          img: "photo-1475452779376-caebfb988090-740x400.jpeg",
          category: "Bicycling",
          difficulty: "Beginner",
          length: "6 Lectures",
          hours: "6 hours",
          price: "29$",
          special: false,
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
  background-color: #e4e7e7;

  .container {
    padding: 20px 0;

    h2 {
      text-align: center;
      margin: 20px 0;
    }
    .cards {
      width: 80%;
      margin: auto;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-evenly;
    }

    .bottom {
      text-align: center;

      button {
        margin: 20px 0;
        padding: 10px 20px;
        background-color: #f2b71d;
        border-radius: 20px;
        border: none;
        color: white;
        font-size: 20px;
        cursor: pointer;
      }
    }
  }
}
</style>
