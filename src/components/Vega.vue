<script setup lang="ts">
import { nextTick } from 'vue';

defineProps<{ msg: string }>()

import { loadOml2d } from 'oh-my-live2d';
loadOml2d({
  models: [
    {
      "path": 'https://model.oml2d.com/cat-black/model.json',
      "scale": 0.15,
      "position": [0, 20],
      "stageStyle": {
        "height": 350
      }
    },
    {
      "path": 'https://model.oml2d.com/cat-white/model.json',
      "scale": 0.15,
      "position": [0, 20],
      "stageStyle": {
        "height": 350
      }
    }
  ]
  // ...options
});




function getDayOfWeek() {
  const today = new Date();
  const dayOfWeek = today.getDay();
  // getDay() 返回的是0（星期日）到6（星期六）的值
  return dayOfWeek;
}

function highlightCurrentDay() {
  const daysContainer = document.getElementById('days') as HTMLElement;
  const days = daysContainer.getElementsByClassName('day');

  // 移除所有行内块的激活状态
  Array.from(days).forEach(day => {
    day.classList.remove('active');
  });

  // 根据当前星期几，放大对应的行内块
  const currentDay = getDayOfWeek();
  const activeDay = days[currentDay - 1];
  if (activeDay) {
    activeDay.classList.add('active');
  }
}

nextTick(() => {//nextTick，不一定要用在onMounted里
  highlightCurrentDay();
});
loadOml2d;

// 当页面加载完成后执行

</script>


<template>

  <div class="VegaMaidCoffee">
    <div class="CoffeeTitle">
      <h1>VEGA</h1>
      <h1>coffee</h1>
    </div>
  </div>
  <div class="CoffeeModule">
    CoffeeModuleTitle
    <div class="ModuleContent">
      <div class="ModuleColumn">
        CoffeeModule1
        <div>

        </div>
      </div>
      <div class="ModuleColumn">
        CoffeeModule2
      </div>
      <div class="ModuleColumn">
        CoffeeModule3
      </div>
      <div class="ModuleColumn">
        CoffeeModule4
      </div>
    </div>
  </div>


  <div class="schedule">
    <div class="scheduleTitle">
      <h2>值班表</h2>
    </div>

    <div id="days">
      <span class="day day1" data-day="1">星期一</span>
      <span class="day day2" data-day="2">星期二</span>
      <span class="day day3" data-day="3">星期三</span>
      <span class="day day4" data-day="4">星期四</span>
      <span class="day day5" data-day="5">星期五</span>
      <span class="day day6" data-day="6">星期六</span>
      <span class="day day7" data-day="7">星期日</span>
    </div>
  </div>
  <div>

  </div>
</template>

<style scoped>
.VegaMaidCoffee {
  height: 100vh;
  text-align: center;
  background: url(../assets/CoffeeGenshin.webp) no-repeat;
  background-size: 100% 100%;
  border-bottom: 0px rgb(186, 85, 23) solid;
}

.CoffeeTitle {
  font-family: futura-pt, 游ゴシック体, YuGothic, 游ゴシック, "Yu Gothic", メイリオ, sans-serif;
  font-weight: bold;
  padding-top: 20%;
  color: bisque;
}

.CoffeeModule {
  text-align: center;
  /* background-image: linear-gradient(to top, #a8edea 0%, #fed6e3 100%); */
  font-size: 5vh;
}

.ModuleContent {
  font-size: 3vh;
  width: 100%;
}

.ModuleColumn {
  width: 25%;
  text-align: center;
  min-width: 160px;
  display: inline-block;
}


.toparea {
  background-color: rgb(33, 32, 32);
  height: 50px;
  border-bottom: 10px rgb(186, 85, 23) solid;
  line-height: 50px;
  color: antiquewhite;
  width: 100%;
}

#days {
  text-align: center;
}

.day {
  display: inline-block;
  width: 12%;
  height: 30vh;
  min-width: 80px;
  margin-top: 50px;
}

.day1 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day2 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day3 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day4 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day5 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day6 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day7 {
  /* background: url(./src/assets/employee.png) no-repeat; */
}

.day.active {
  transform: scale(1.5);
  /* 放大到1.5倍 */
}

.schedule {
  background: linear-gradient(to bottom, #FFD194, #D1913C);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  box-sizing: border-box;
  width: 100%;
  text-align: center;
}
</style>
