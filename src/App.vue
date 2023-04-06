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
  <BaseSelect label="Seleziona categoria" v-model="event.categories" :options="categories"></BaseSelect>

    <h3 class="subtitle is-3">
      Animali ammessi
    </h3>
    <BaseRadioButton label="Si" v-model="event.anuimals" :value="1"></BaseRadioButton>
    <BaseRadioButton label="No" v-model="event.anuimals" :value="0"></BaseRadioButton>
    <h3 class="subtitle is-3">
     Extra
    </h3>
    <BaseCheckbox label="Musica Live" v-model="event.extra.music"></BaseCheckbox>

<BaseCheckbox label="Spettacolo" v-model="event.extra.show"></BaseCheckbox>
  <button class="button is-info" type="submit">Crea</button>
  </form>
</div>
</template>

<script>
import BaseInput from "@/components/BaseInput";
import BaseSelect from "@/components/baseSelect";
import BaseCheckbox from "@/components/BaseCheckbox";
import BaseRadioButton from "@/components/BaseRadioButton";
export default {
  name: 'App',
  components: {
    BaseRadioButton,
    BaseCheckbox: BaseCheckbox,
    BaseSelect,
    BaseInput
  },
  data(){
    return{
      event: {
        name:'',
        description: '',
        animals: 1,
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
