<template>
  <div class="clock">
    <div
      class="hand clock__hour-hand"
      :style="{ transform: 'rotate(' + hour * 30 + 'deg)' }"
    ></div>
    <div
      class="hand clock__min-hand"
      :style="{ transform: 'rotate(' + minute * 6 + 'deg)' }"
    ></div>
    <div
      class="hand clock__second-hand"
      :style="{ transform: 'rotate(' + second * 6 + 'deg)' }"
    ></div>
  </div>
</template>

<script setup>
defineProps({
  hour: {
    type: Number,
    default: 0,
  },
  minute: {
    type: Number,
    default: 0,
  },
  second: {
    type: Number,
    default: 0,
  },
});
</script>

<style scoped lang="scss">
.clock {
  width: 10rem;
  height: 10rem;
  border-radius: 50%;
  border: 3px solid #fff;
  box-shadow: 0 6px 20px #ccc;
  margin: 4rem 0 5rem;
  position: relative;

  &::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 4px;
    height: 4px;
    border-radius: 50%;
    border: 2px solid #c14040;
    z-index: 22;
    background-color: #eaeaea;
  }

  .hand {
    width: 1.5px;
    height: 50%;
    background: #4c4c4c;
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%) rotate(180deg);
    transform-origin: bottom;
    transition: transform 0.4s ease;
  }

  .hand.clock__hour-hand {
    height: 30%;
    margin-top: 20%;
    transform: translateX(-50%) rotate(180deg);
    z-index: 3;
  }

  .hand.clock__min-hand {
    height: 40%;
    margin-top: 10%;
    transform: translateX(-50%) rotate(130deg);
    z-index: 10;
  }

  .hand.clock__second-hand {
    height: 40%;
    margin-top: 10%;
    transform: translateX(-50%) rotate(60deg);
    background: #c14040;
  }
}
</style>
