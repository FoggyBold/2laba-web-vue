<template>
  <div class="container">
    <div class="progress-bar">
      <div class="progress-bar__outer">
          <div class="progress-bar__inner" :style="{'width' : percentage + '%', 'background-color' : color}"></div>
      </div>
      <div class="progress-bar__text">{{ percent }}%</div>
    </div>
    <div class="button-group">
      <button class="button-group__button" type="button" @click="decrease">-10</button>
      <button class="button-group__button" type="button" @click="increase">+10</button>
    </div>
  </div>
</template>

<script>
    export default{
      name:"ProgressBar",
      props: {
        startValue: {
          type: Number,
          default: 0,
        }
      },
      data: () => {
        return {
          percentage: 0
        }
      },
      computed : {
        percent() {
          return this.percentage.toFixed()
        },
        color() {
          if(this.percentage <= 10){
            return "#ff2b00";
          }
          else if(this.percentage <= 20){
            return "#ff5500";
          }
          else if(this.percentage <= 30){
            return "#ff8000";
          }
          else if(this.percentage <= 40){
            return "#ffaa00";
          }
          else if(this.percentage <= 50){
            return "#ffd500";
          }
          else if(this.percentage <= 60){
            return "rgb(255, 255, 0)";
          }
          else if(this.percentage <= 70){
            return "#d5ff00";
          }
          else if(this.percentage <= 80){
            return "#aaff00";
          }
          else if(this.percentage <= 90){
            return "#80ff00";
          }
          else{
            return "#55ff00";
          } 
        } 
      },
      methods: {
        decrease() {
          this.percentage = this.percentage - 10;
          if(this.percentage < 0){
            this.percentage = 0;
          }
        },
        increase() {
          this.percentage = this.percentage + 10;
          if(this.percentage > 100){
            this.percentage = 100;
          }
        }
      }
    }
</script>

<style scoped lang="less">  
  .progress-bar {
    display: flex;
    align-items: center;

    &__text {
      color: #3c3f59;
      font-size: 18px;
      display: table-row;
      padding-left: 8px;
    }

    &__outer {
      position: relative;
      width: 350px;
      border-radius: 100px;
      overflow: hidden;
      height: 6px;
      background-color: rgb(212, 206, 206);
    }

    &__inner {
      height: 100%;
      transition: .6s;
      border-radius: 100px;
      width: 200px;
      background-color: red;
    }
  }

  .button-group {
    text-align: left;

    &__button {
      width: 50px;
    }
  }
</style>