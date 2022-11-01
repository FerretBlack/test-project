<template>
  <div>
    <button @click="setDecrement" class="minus-button">-</button>
    <button @click="setIncrement" class="plus-button">+</button>

    <div class="counter">
      {{ number }}
    </div>

    <p>Это тестовый проект</p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const number = ref(0);

    const setIncrement = () => {
      number.value = number.value + 1;
      console.log(number.value);
    };

    const setDecrement = () => {
      number.value -= 1;
      console.log(number.value);
    };

    return {
      number,
      setIncrement,
      setDecrement,
    };
  },
};
</script>

<style>
.plus-button {
  background: #63eb79;
  border: none;
  min-width: 80px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 24px;
  cursor: pointer;
}

.minus-button {
  background: #ff8f8f;
  border: none;
  min-width: 80px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 24px;
  cursor: pointer;
  margin-right: 10px;
}

.counter {
  width: 160px;
  height: auto;
  background: #f6f6f6;
  border: 2px solid black;
  text-align: center;
  margin-top: 10px;
}
</style>
