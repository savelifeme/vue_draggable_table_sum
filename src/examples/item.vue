<template>
  <draggable-container class="topCon">
    <draggable-child v-for="item in initialChildren" :key="item.id" :id="item.id" :width="item.width"
      :height="item.height" @stop="handleStop" @start="handleStart" @drag="handleDrag" @resize="handleResize"
      :default-position="item.position">
      <div class="item" :style="{
        display: 'flex',
        flexDirection: 'column',
        justifyContent: 'center',
        alignItems: 'center',
        cursor: 'move',
        boxSizing: 'border-box',
        background: item.background,
      }">
        <span>size: {{ item.size }}</span>
        <span>drag me</span>
      </div>
    </draggable-child>
  </draggable-container>
</template>
<script>
export default {
  data() {
    return {
      initialChildren: [
        {
          id: 1,
          background: "#88f",
          width: 100,
          height: 100,
          position: { x: 100, y: 10 },
        },
      ],
    };
  },
  methods: {
    handleResize(e) {
      console.log(e, "handleResize");
    },
    handleDrag(e) {
      console.log(e);
    },
    handleStop(e) {
      console.log(e, "handleStop");
    },
    handleStart() {
      console.log("开始");
    },
    handleClick() {
      alert(1);
    },
  },
};
</script>
<style scoped>
.topCon {
  width: 320px;
  border-right: 1px solid rgb(248, 206, 206);
}
</style>
