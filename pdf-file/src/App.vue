<template>
  <div id="app">
    <input type="text" v-model="name" placeholder="text">
    <button @click="generatePdf" type="button">Generate PDF</button>  
    </div>
</template>

<script>
import jsPDF from 'jspdf'


export default {
  name: 'App',

    data() {
            return {
                name: ''
            }
        },
  methods: {
    generatePdf(){
      // let pdfName = 'test';
      //iniciar uma nova instancia em jspdf,, que é a dependencia q gera arquivo em pdf em sim
     const doc = new jsPDF(); //armazena em uma const o import

     doc.text(this.name, 15, 15);//name que é o v-model, com 15 q é algo de cordenadas

      //save the document
     doc.save('.pdf') //salva o documento em formato pdf assim
   },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
