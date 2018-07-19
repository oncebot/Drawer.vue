<template>
  <div id="app">
      <Drawer :direction="'left'" :exist="true" ref="LeftDrawer">Left Drawer</Drawer>
      <Drawer :direction="'right'" :exist="true" ref="RightDrawer">Right Drawer</Drawer>
      <div>
        <h1>Drawer.vue</h1>
        <p>Simple touch enabled drawer component for vue.js.</p>
        <p>Try on any touch device for the touch open demo</p>
        <div>
          <button @click="openLeft" style="margin-right: 12px;">Open left</button>
          <button @click="openRight">Open Right</button>
        </div>
      </div>
  </div>
</template>

<script>
import Drawer from './components/Drawer.vue'

export default {
  name: 'app',
  components: {
    'Drawer':Drawer
  },
  methods:{
    openLeft(){
      if(!this.$refs.LeftDrawer.active){
        this.$refs.LeftDrawer.open();        
      }else{
        this.$refs.LeftDrawer.close();
      }
    },
    openRight(){
      if(!this.$refs.RightDrawer.active){
        this.$refs.RightDrawer.open();        
      }else{
        this.$refs.RightDrawer.close();
      }
    },
  }
}
</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
}
</style>
