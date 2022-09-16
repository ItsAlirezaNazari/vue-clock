<template>
  <div class="time card__time">
    <input
      type="text"
      class="time__hour"
      value="00"
      maxlength="2"
      @change="onHourChange($event.target.value)"
    />

    <span class="time__sep">:</span>

    <input
      type="text"
      class="time__minute"
      value="00"
      maxlength="2"
      @change="onMinuteChange($event.target.value)"
    />

    <span class="time__sep">:</span>

    <input
      type="text"
      class="time__second"
      value="00"
      maxlength="2"
      @change="onSecondChange($event.target.value)"
    />
  </div>
</template>

<script setup>
const emit = defineEmits(["hourChange", "minuteChange", "secondChange"]);

function onHourChange(value) {
  emit("hourChange", Number(value));
}

function onMinuteChange(value) {
  emit("minuteChange", Number(value));
}

function onSecondChange(value) {
  emit("secondChange", Number(value));
}
</script>

<style lang="scss" scoped>
.time {
  margin-bottom: 1.75rem;
  font-size: 1.75rem;

  .time__sep {
    display: inline-block;
    vertical-align: middle;
    margin-top: -1rem;
  }

  .time__hour,
  .time__minute,
  .time__second {
    box-sizing: border-box;
    position: relative;
    background-color: transparent;
    font-size: 2.25rem;
    width: 2.5rem;
    height: 2.5rem;
    user-select: none;
    font-family: "Barlow", sans-serif;
    caret-color: transparent;
    transition: all 0.1s;
    text-align: center;

    &:focus {
      border-bottom: 2px solid blue;
      height: calc(2.5rem - 2px);
    }
  }
}
</style>
