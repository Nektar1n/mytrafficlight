<template id="light">
  <div v-bind:class="color" class="light__signal">
    <div v-bind:class="{ active: isActive, blink: isBlink }" class="light__dim-layer"></div>
    <span v-if="isActive" v-bind:class="{ 'text-blink': isBlink }" class="light__timer">{{ time }}</span>
  </div>
</template>

<script>
export default {
  name: 'Light',
  props: {
    color: {
      type: String
    },
    isActive: {
      type: Boolean
    },
    time: {
      type: Number
    },
    isBlink: {
      type: Boolean
    }
  }
}
</script>

<style scoped>
.light__signal {
  width: 100px;
  height: 100px;
  background-color: #fff;
  border-radius: 50px;
  position: relative;
}

.red {
  color: red;
  background: red;
  background-color: red;
  background-size: 5px 5px;
}

.yellow {
  color: yellow;
  background: yellow;
  background-color: yellow;
  background-size: 5px 5px;
}

.green {
  color: green;
  background-color: green;
  background: green;
}

.light__dim-layer {
  width: 100%;
  height: 100%;
  border-radius: 100%;
  background-color: #000;
  opacity: 0.7;
}

.active {
  opacity: 0;
}

.light__timer {
  font-size: 60px;
  line-height: 100px;
  position: fixed;
  top: 550px;
  left: 642px;
  width: 10%;
  color: black;
  background-color: burlywood;
  border: 6px solid black;

}

.text-blink {
  animation: textBlink 2s infinite;
}

@keyframes textBlink {
  0% { color: inherit; }
  25% { color: #fff; }
  50% { color: inherit; }
  75% { color: #fff; }
  100% { color: inherit; }
}

.blink {
  animation: blink 2s infinite;
}

@keyframes blink {
  0% { opacity: 0.7 }
  25% { opacity: 0.1 }
  50% { opacity: 0.7 }
  75% { opacity: 0.1 }
  100% { opacity: 0.7 }
}
</style>
