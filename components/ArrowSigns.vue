<template>
  <div>
    <div class="frame">
      <div
        class="arrow"
        :class="{ 'moving-arrow': isMove, 'stop-arrow': !isMove }"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMove: false,
    }
  },
  methods: {
    startAnimation() {
      this.isMove = true
    },
    stopAnimation() {
      this.isMove = false
    },
  },
}
</script>

<style scoped>
.frame {
  margin: auto;
  width: 100px;
  height: 100px;
}
.arrow {
  width: 50px;
  height: 50px;
}
.stop-arrow {
  border: solid 0.6em;
  border-color: black transparent transparent black;
  transform: translate(0%, 50%) rotate(135deg);
}
.moving-arrow {
  animation-duration: 0.8s;
  animation-name: arrow-anim;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}
@keyframes arrow-anim {
  from {
    border: solid 0.6em;
    border-color: black transparent transparent black;
    transform: translate(0em, 50%) rotate(135deg);
  }
  to {
    border: solid 0.6em;
    border-color: transparent transparent transparent transparent;
    transform: translate(1.5em, 50%) rotate(135deg);
  }
}
</style>
