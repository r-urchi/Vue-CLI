<template>
  <div class="container">
    <h2>{{ msg }}</h2>
    <div class="counter__container">
        <button v-on:click=subtract() class="counter__btn">-</button>
        <input type="number" v-bind:value="counterValue" class="counter__value" disabled/>
        <button v-on:click=add() class="counter__btn">+</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    msg: String
  },
  data:function() {
    return {
      counter: 0,
    };
  },
  methods:{
    add(){
        this.counter++;
    },
    subtract(){
        this.counter === 0 ? this.counter = 0 : this.counter--;
    },
  },
  computed:{
    counterValue(){
        return this.counter;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.counter__container {
  width: 15rem;
  height: 8rem;
  background: #DFD8CA;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10px;
}

.counter__container .counter__value, .counter__container .counter__btn {
  width: 2rem;
  text-align: center;
  height: 2rem;
  margin: 0 0.1rem;
}

.counter__container .counter__btn {
  border: none;
  background: #B91646;
  color: #DFD8CA;
  cursor: pointer;
  font-size: 1.5rem;
}
</style>
