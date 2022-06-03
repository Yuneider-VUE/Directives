<template>
  <div class="center">
    <div :class="input" >
      <h1 >{{name}}</h1>
      <input type="text" v-model="input"/>
      <h3 v-text="code"></h3>
      <img :src="img"/>
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
      input: 'darkMode o lightMode',
      img: "https://picsum.photos/200/300",
      grid: "grid"
    }
  },
}
</script>


<style>
.center{
  display: flex;

  justify-content: center;
  align-items: center;
}
.darkMode{
  display: grid;

  margin-top: 50px;
  padding: 50px;

  place-items: center;

  color: lightgray;
  background: darkslategray;
}
.lightMode{
  display: grid;

  margin-top: 50px;
  padding: 50px;

  place-items: center;
  
  color: darkslategray;
  background: lightgray;
}
</style>
