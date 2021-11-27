<template>
  <div class="container">
    <h2>{{ msg }}</h2>

        <div class="table__container">

            <button class="mode" v-on:click=darkMode()>{{changeMode}}</button>
            
            <div v-bind:class="mode ? 'darkMode' : 'lightMode'" > 

                <table class="table">
                  <tr class="table__tr">
                    <th class="table__th">N°</th>
                    <th class="table__th">Producto</th>
                    <th class="table__th">Tipo</th>
                  </tr>
                  <tr v-for="product in products" v-bind:key="product.id">
                    <td>{{product.id}}</td>
                    <td>{{product.product}}</td>
                    <td>{{product.type}}</td>
                  </tr>
                </table>

            </div>
        </div>

  </div>
</template>

<script>
export default {
  name: 'Table',
  props: {
    msg: String
  },
  data:function() {
    return {
      mode: false,
      products: [
        {
          id: 1,
          product: "Guitarra",
          type: "Les Paul",
        },
        {
          id: 2,
          product: "Bajo",
          type: "Jazzbass",
        },
        {
          id: 3,
          product: "Guitarra acústica",
          type: "Classic",
        },
        {
          id: 4,
          product: "Bajo acústico",
          type: "Classic",
        },
        {
          id: 5,
          product: "Guitarra",
          type: "Stratocaster",
        },
      ],
    };
  },
  methods:{
    darkMode(){
        this.mode = !this.mode;
    }
  },
  computed:{
    changeMode(){
        return this.mode ? 'Modo claro' : 'Modo oscuro';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.darkMode {
  background: #000;
  color: #fff;
}

.lightMode {
  background: #fff;
  color: #000;
}

.table__container {
  min-width: 50vmin;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.table__container .table {
  width: 50vw;
  padding: 1rem;
}

.table__container .table .table__th {
  text-align: left;
}

.table__container .mode {
  width: 8rem;
  height: 3rem;
  border: none;
  background: #B91646;
  border-radius: 0.5rem;
  color: #fff;
  margin-bottom: 1rem;
}
</style>
