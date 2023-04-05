<template>
<div  class="container">
  <h2 class="title is-2">
    Crea un evento
  </h2>
  <form>

<BaseInput label="Nome" v-model="event.name"></BaseInput>

    <h3 class="subtitle is-3">
      Che tipo di evento
    </h3>
   <BaseInput label="Descrizione" v-model="event.description"></BaseInput>

    <h3 class="subtitle is-3">
      Dove si svolgerà l' evento?
    </h3>
   <BaseInput label="Luogo" v-model="event.location"></BaseInput>
  <base-select label="Seleziona categoria" v-model="event.category" :options="categories"></base-select>

    <h3 class="subtitle is-3">
      Animali ammessi
    </h3>
    <div class="field">
      <div class="control">
        <label class="radio" >
          <input  type="radio" name="animals"  v-model="event.animals" :value="1">
        Si
        </label>
        <label class="radio" >
          <input  type="radio" name="animals" v-model="event.animals" :value="0">
          No
        </label>
      </div>
    </div>

    <h3 class="subtitle is-3">
     Extra
    </h3>
    <div class="field">
      <div class="control">
        <label class="checkbox mr-5">
          <input  type="checkbox"  v-model="event.extra.music">
         Live Music
        </label>

        <label class="radio" >
          <input  type="checkbox" v-model="event.extra.show">
         Spettacolo
        </label>
      </div>
    </div>

  <button class="button is-info" type="submit">Crea</button>
  </form>
</div>
</template>

<script>
import BaseInput from "@/components/BaseInput";
import BaseSelect from "@/components/baseSelect";
export default {
  name: 'App',
  components: {
    BaseSelect,
    BaseInput
  },
  data(){
    return{
      event: {
        name:'',
        description: '',
        animals: 1,
        category: '',
        location:'',
        extra:{
          music:false,
          show:false
        }

      },
      categories: [
        'Natura',
        'Educazione',
        'Comunità',
        'Cibo',
        'Musica',
        'Cultura',
        'Ambiente'
      ],
    }
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
