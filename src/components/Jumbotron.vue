<template>
  <section>
    <div class="jumbo">
      <div class="container_60">
        <div class="container_40">
          <h2>Start your Human <span>Revolution </span>today</h2>
          <h4>
            A wonderful serenity has taken possession of my entire soul, like
            these sweet mornings of spring which I enjoy with my whole heart
          </h4>
        </div>
      </div>
      <div class="subscribe">
        <div class="left">
          <h3>
            Limited Sale: <span>All Courses with {{ sale }}% off</span>
          </h3>
          <input type="text" placeholder="Enter your E-mail" />
          <button>SUBSCRIBE</button>
        </div>
        <div class="right">
          <ul>
            <li>
              {{ days }}
              <span>Days</span>
            </li>
            <li>
              {{ hours }}
              <span>Hours</span>
            </li>
            <li>
              {{ minutes }}
              <span>Minute</span>
            </li>
            <li>
              {{ seconds }}
              <span>Second</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

export default {
  name: "Jumbotron",
  data: function () {
    return {
      sale: 55,
      secondSet: 1000,
      minuteSet: 60000,
      hourSet: 3600000,
      daySet: 86400000,
      secondsPrint: 0,
      minutesPrint: 0,
      hoursPrint: 0,
      daysPrint: 0,
      show: true,
      now: new Date(),
      end: new Date (2022,11,19,14,30),
      distance: 0,
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  },
  mounted(){
      this.showRemainingTime
  },
  methods: {
    showRemainingTime: function () {
        const timer = setInterval(() =>{
            this.distance = this.end.getTime() - this.now.getTime();

            if(this.distance < 0){
                clearInterval(timer);
                return
            };

            this.days = Math.floor((this.distance / this.daySet));
            this.hours = Math.floor((this.distance % this.daySet) / this.hourSet);
            this.minutes = Math.floor((this.distance % this.hourSet) / this.minuteSet);
            this.seconds = Math.floor((this.distance % this.minuteSet) / this.secondSet);

            this.daysPrint = this.days < 10 ? '0' + this.days : this.days;
            this.hoursPrint = this.hours < 10 ? '0' + this.hours : this.hours;
            this.minutesPrint = this.minutes < 10 ? '0' + this.minutes : this.minutes;
            this.secondsPrint = this.seconds < 10 ? '0' + this.seconds : this.seconds
        }, 1000)
    },
  },
  created: {
    startTimer: function(){
        this.showRemainingTime();
    }
  },
};
</script>

<style lang="scss" scoped>
@import "../style/general.scss";
@import "../style/common.scss";
section {
  width: 100%;
  padding-top: 150px;

  .jumbo {
    background-image: url("../assets/img/slide-1.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 835px;

    .container_60 {
      display: flex;
      height: 835px;
      flex-direction: column;
      justify-content: center;
      align-items: flex-end;

      .container_40 {
        width: 40%;
      }

      h2 {
        font-size: 50px;
        margin: 50px 0;

        span {
          color: #f2b71d;
        }
      }
    }

    .subscribe {
      width: 1500px;
      margin: auto;
      height: 250px;
      display: flex;
      align-items: center;
      justify-content: space-evenly;
      background-color: #f2b71d;
      padding: 10px 20px;
      border-radius: 20px;
      position: relative;
      bottom: 100px;

      .left {
        h3 {
          color: white;
          font-size: 35px;
          margin: 20px;
        }

        input {
          height: 50px;
          width: 500px;
          border-radius: 30px;
          padding: 5px 20px;
          border: none;
        }

        button {
          background-color: #0d2229;
          border: none;
          height: 50px;
          padding: 5px 20px;
          font-size: 15px;
          border-radius: 30px;
          position: relative;
          right: 40px;
          color: white;
          cursor: pointer;
        }
      }

      .right {
        ul {
          list-style: none;
          display: flex;

          li {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin: 0 30px;
            width: 100px;
            font-size: 30px;
            color: white;

            span {
              color: black;
            }
          }
        }
      }
    }
  }
}
</style>
