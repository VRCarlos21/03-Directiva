<template>
  <div>
    <h1>Directivas</h1>
    <hr/>
    
    <h1>v-text</h1>
    <span v-text="titulo" ></span>
    <h1>{{titulo}}</h1>
    <hr/>


    <h1>v-show</h1>
    <h3>tu edad es : {{edad}}</h3>
    <h2 v-show="edad>=18" >Mayor de edad</h2>
    <h2 v-show="edad<18" >Menor de edad</h2>
    <hr/>


    <h1>v-if v-else-if vi-else</h1>
    <h3>tu edad es : {{edad}}</h3>
    <h2 v-if="edad>=18 && edad >0 && edad<100" >mayor de edad</h2>
    <h2 v-else-if="edad<18 && edad >0 && edad<100" >menor de edad</h2>
    <h2 v-else >Edad invalida</h2>



    <button @click="inc()">incrementar</button>
    <button @click="dis()">disminuir</button>

    <h1>v-html</h1>
    <div v-html="html" ></div>
    <hr/>
   
    <h1>v-for</h1>  
    <ul>
      <li>{{ usuarios[0] }}</li>
      <li>{{ usuarios[1] }}</li>
      <li>{{ usuarios[2] }}</li>
      <li>{{ usuarios[3] }}</li>
    </ul>
    <ul>
      <li v-for="usuario in usuarios" >{{usuario}}</li>
    </ul>
    <ul>
      <li v-for="(usuario,index) in usuarios" > {{index}}.{{usuario}}</li>
    </ul>
    <ul>
      <li v-for="(usuario,index) in usuarios"  key="index" > {{index}}.{{usuario}}</li>
    </ul>
    <ul>
      <li v-for="(valor,clave) in uusuarios"  key="clave" > {{clave}}:{{valor}}</li>
    </ul>
<hr>
<h1>v-bind</h1>
<img v-bind:src="url" alt="no hay internet">

  </div>

  <br/>
  <h1>v-on</h1>
  <div @dblclick="click" class="contador">
    Clicks:{{clicks}}
  </div>
</template>

<script>
  export default{
    data: () => ({
      titulo: 'Hola desede vue3',
      html: "<h3>Soy un H3</h3>",
      edad:0,
      usuarios:["Melisa", "Fernando", "Raul", "José"],
      uusuarios:{nombre: "Yirsis"},
      clicks: 0,
      url:"https://cdn.svgporn.com/logos/nextjs-icon.svg",


    }),
    methods:{
      inc(){
        this.edad++;
      },
      dis(){
        this.edad--;
      },
      click(){
        this.clicks++;
      }
    },
  };
</script>
<style scoped>
  div{
    text-align: center;
    margin: 0px 2rem;
  }
  h2{
    color: brown;
  }
  .contador{
    background: pink;
    color: snow;
    font-weight: bold;
    height: 400px;
  }
</style>
