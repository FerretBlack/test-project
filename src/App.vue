<template>
  <div>
    <button @click="setDecrement" class="minus-button">-</button>
    <button @click="setIncrement" class="plus-button">+</button>

    <div class="counter">
      {{ number }}
    </div>

    <p>Это тестовый проект!</p>

    <div class="block">
      <div class="container">
        {{ text }}
      </div>

      <div class="wrapper">
        <input v-model="inputText" class="input-text" />
        <button @click="send" class="input-button">Отправить</button>
      </div>
    </div>
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

    const text = ref("Тестовый текст");
    const inputText = ref(null);

    const send = () => {
      text.value = inputText.value;
      inputText.value = "";
    };

    return {
      number,
      setIncrement,
      setDecrement,
      text,
      inputText,
      send,
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

.block {
  width: 50%;
}

.container {
  background: gray;
  padding: 50px;
  border-radius: 10px;
  color: white;
  text-align: center;
}

.wrapper {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  width: 100%;
  margin-top: 10px;
}

.input-text {
  width: 100%;
}

.input-button {
  width: 50%;
}
</style>
