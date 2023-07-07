<template>
  <div class="box">
    <item></item>
    <draggable-container>
      <draggable-child v-for="item in initialChildren" :key="item.id" :id="item.id" :width="item.width"
        :height="item.height" @stop="handleStop" @start="handleStart" @drag="handleDrag" @resize="handleResize"
        :default-position="item.position" :draggable="item.draggable">
        <div class="item" :style="{
          display: 'flex',
          flexDirection: 'column',
          justifyContent: 'center',
          alignItems: 'center',
          cursor: 'move',
          boxSizing: 'border-box',
          background: item.background,
          border: item.border
        }">
          <span>size: {{ item.width }}*{{ item.height }}</span>
          <span>{{ item.title }}</span>
        </div>
      </draggable-child>
    </draggable-container>
  </div>
</template>
<script>
// import draggableContainer from '../package/DraggableContainer';
// import draggableChild from '../package/DraggableChild';
import item from './item.vue';
import { h, cloneVNode } from 'vue'

export default {
  components: {
    item
    //     draggableContainer,
    //     draggableChild
  },
  data() {
    return {
      initialChildren: [
        // { id: 1, background: '#8d6', width: 150, height: 150, position: { x: 10, y: 10 }, draggable: false, title: '模板' },
        // { id: 2, background: '#8ce8df', width: 150, height: 150, position: { x: 400, y: 106 }, draggable: true, title: 'drag me1' },
        // { id: 3, background: '#d2aff6', width: 150, height: 150, position: { x: 100, y: 316 }, draggable: true, title: 'drag me2' },
        // { id: 4, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 5, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 6, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 7, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 8, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 9, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 10, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 11, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 12, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 13, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 14, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
        // { id: 15, background: '#fee493', width: 150, height: 150, position: { x: 480, y: 376 }, draggable: true, title: 'drag me3' },
      ]
    };
  },
  methods: {
    handleResize(e) {
      console.log(e, 'handleResize');
    },
    handleDrag(e) {
      console.log(e);
    },
    handleStop(e) {
      console.log(e, 'handleStop');
      // console.log(cloneVNode(item))
    },
    handleStart() {
      console.log('开始');
    },
    handleClick() {
      alert(1);
    },
    initNum() {
      const arr = []
      for (let i = 1; i < 90; i++) {
        arr.push({
          id: i,
          background: '#fee493',
          width: 150,
          height: 32,
          position: { x: 10, y: 10 },
          draggable: true,
          title: '',
          border: '1px solid #333'
          
        })
      }
      return arr
    }
  },
  mounted() {
    this.initialChildren = this.initNum();
  },
};
</script>
<style scoped>
.box {
  display: flex;
}
</style>