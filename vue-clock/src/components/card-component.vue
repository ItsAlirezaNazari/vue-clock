<template>
  <div class="card">
    <clock-component
      :hour="hour"
      :minute="minute"
      :second="second"
    ></clock-component>

    <digital-component
      @hourChange="changeHour"
      @minuteChange="changeMinute"
      @secondChange="changeSecond"
    ></digital-component>

    <p class="card__description">
      Select a section from a digital clock then change value from analog clock
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";
import ClockComponent from "./clock-component.vue";
import DigitalComponent from "./digital-component.vue";

let hour = ref(0);
let minute = ref(0);
let second = ref(0);

function changeHour(value) {
  hour.value = value;
}

function changeMinute(value) {
  minute.value = value;
}

function changeSecond(value) {
  second.value = value;
}
</script>

<style scoped lang="scss">
.card {
  width: 16.5rem;
  padding: 4rem 2rem;
  background-color: #eaeaea;
  border-radius: 1.5rem;
  overflow: hidden;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2),
    inset -8px 0 16px 0 rgba(0, 0, 0, 0.2),
    inset 8px 8px 16px 0 rgba(255, 255, 255, 1),
    inset 8px -8px 16px 0 rgba(255, 255, 255, 1);
  display: flex;
  align-items: center;
  flex-direction: column;
  text-align: center;

  .card__description {
    font-size: 0.75rem;
    color: #888;
  }
}
</style>
