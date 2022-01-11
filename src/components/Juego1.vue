<template>
  <v-main>
    <v-container>
      <v-row>
        <v-col cols="4" >
          <v-text-field v-model="numero1" type="number" label="Numero al Arreglo" ></v-text-field>
        </v-col>
        <v-col cols="4">
          <v-btn @click="pushArreglo">Agregar al Arreglo</v-btn>
        </v-col>
        <v-col cols="4">

          [
            <span v-for="nro in arreglo1" v-bind:key="nro">{{nro}},
            </span>
          ]
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="4">
          Suma : <v-text-field v-model="suma"></v-text-field>
        </v-col>
        <v-col cols="4">
          <v-btn @click="calcular">Calcular</v-btn>
        </v-col>
        <v-col cols="4">

          [
          <span v-for="nros in arreglo2" v-bind:key="nros">
            {{nros}},
            </span>
          ]
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    arreglo1:[],
    arreglo2:[],
    numero1:0,
    resultado:false,
    suma:0
  }),
  methods:{
    pushArreglo(){
        this.arreglo1.push(Number(this.numero1))
    },
    calcular(){
      var i,j,n;
      this.arreglo2 = []
      this.resultado = false
      n = this.arreglo1.length
      for(i = 0; i<n; i++){
        for(j=i+1;j<=n; j++){
          if(!this.resultado){
          let sum = Number(this.arreglo1[i]) + Number(this.arreglo1[j])
            if(Number(sum) === Number(this.suma)){
              this.resultado = true
              this.arreglo2.push(Number(this.arreglo1[i]))
              this.arreglo2.push(Number(this.arreglo1[j]))
              console.log(this.arreglo2)
            }
          }
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
