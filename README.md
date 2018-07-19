# Drawer.vue
Simple touch enabled drawer component for vue.js.

[Demo](https://oncebot.github.io/Drawer.vue/)

### Usage
Register the drawer component with your desired name.
```
import Drawer from './path/to/Drawer.vue';
Vue.component('Drawer', Drawer);
```


Add <Drawer> component on any page with 3 required attributes:
	1. direction : 'left' or 'right' depending on which side you want the drawer
	2. exist : true or false depending on if you want it to exist on the page or not
```
<Drawer :direction="'left'" :exist="true">Menu content goes here</Drawer>
```

To trigger open and close events from outside use ref and trigger .open() or .close() methods.
You can also use active property to check if the menu is already opened or not.
```
<template>
  <div class="about">
    <h1>Page heading</h1>
    <button @click="openMenu">Click</button>

    <Drawer :direction="'left'" :exist="true" ref="LeftDrawer">left</Drawer>
  </div>
</template>
<script>
	export default{
		methods:{
			openMenu(){
				if(this.$refs.LeftDrawer.active){
					this.$refs.LeftDrawer.close();					
				}else{
					this.$refs.LeftDrawer.open();
				}
			}
		}
	}
</script>
<style>
</style>
```