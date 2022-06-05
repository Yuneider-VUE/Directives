<template>
  <div>
    <div> 
      <div :style="{left:left+'px',top:top+'px'}" :class="mode" id="div">
        <h1 >{{name}}</h1>
        <select @change="changeMode()" v-model="selectedMode">
          <option value="darkMode">Dark Mode</option>
          <option value="lightMode">Light Mode</option>
        </select>
        <h3 v-text="code"></h3>
        <img :src="img"/>
      </div> 
    </div>
    <div class="button">
      <button @click="moveToLeft()" >LEFT</button>
      <button @click="moveToRight()" >RIGHT</button>
      <button @click="moveToUp()" >UP</button>
      <button @click="moveToDown()" >DOWN</button>
    </div>
  </div>
</template>

<script>
export default{
  name:'App',
  data(){
    return{
      name: 'Yuneider Parada Pérez',
      code: '20191020058',
      img: 'https://picsum.photos/200/300',
      grid: 'grid',
      selectedMode: 'Light Mode',
      mode: 'lightMode',
      left: 0,
      top: 0,
    }
  },
  methods:{
    changeMode(){
      this.mode = this.selectedMode;
    },
    moveToLeft(){
      this.left -= 10;
    },
    moveToRight(){
      this.left += 10;
    },  
    moveToUp(){
      this.top -= 10;
    },
    moveToDown(){
      this.top += 10;
    },
  },
}
</script>


<style>
.button{
  position: absolute;
  z-index: 1;

  left: 45%;
}
.darkMode{
  display: grid;
  position: absolute;

  width: 400px;

  margin-top: 50px;
  padding: 50px;

  place-items: center; 

  color: lightgray;
  background: darkslategray;
}
.lightMode{
  display: grid;
  position: absolute;

  width: 400px;

  margin-top: 50px;
  padding: 50px;

  place-items: center;
  
  color: darkslategray;
  background: lightgray;
}
</style>
