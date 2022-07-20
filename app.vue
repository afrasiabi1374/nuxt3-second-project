<script setup lang="ts">
  import { Gender, Popularity, Length, names } from "@/data"

  interface OptionsState {
    gender: Gender;
    popularity: Popularity;
    length: Length;
  }

  const options = reactive<OptionsState>({
    gender : Gender.GIRL,
    length: Length.SHORT,
    popularity: Popularity.TRENDY,
  })
  const computeSelectedNames = () => {
    const filterNames = names.filter((name)=> name.gender === options.gender)
    .filter((name)=> name.popularity === options.popularity)
    .filter((name) => {
      if (options.length === Length.ALL) return true
      else return name.length === options.length
    })

    selectedNames.value = filterNames.map(name => name.name)

  }
  const selectedNames = ref<string[]>([])
  const optionsArray = [
    {
      title: '1) choose a gender',
      category: 'gender',
      buttons: [Gender.GIRL, Gender.UNISEX, Gender.BOY],
    },
    {
      title: '2) choose a names popularity',
      category: 'popularity',
      buttons: [Popularity.TRENDY, Popularity.UNIQUE],
    },
    {
      title: '3) choose a names length',
      category: 'length',
      buttons: [Length.SHORT, Length.ALL, Length.LONG],
    },
  ]
</script>
<template>
  <div class="container">
    <h1>Baby name generator</h1>
    <p>choose your options and click find name blow </p>
    <div class="options-container">
    <Option
      v-for="option in optionsArray"
      :key="option.title"
      :option="option"
      :options="options"
    />
    <button class="primary" @click="computeSelectedNames">Find Names</button>
    </div>
    <div class="cards-container">
      <div v-for="name in selectedNames" :key="name" class="card" >
        <h4>{{name}}</h4>
        <p>x</p>
      </div>
    </div>

    {{ selectedNames }}
  </div>
</template>
<style>
  .container {
    font-family: Arial, Helvetica, sans-serif;
    color: rgb(27, 60, 138);
    max-width: 50rem;
    margin: 0 auto;
    text-align: center;
  }
  .options-container {
    background-color: rgb(255, 238, 236);
    border-radius: 2rem;
    padding: .1rem;
    width: 95%;
    margin: 0 auto;
    margin-top: 4rem;
    position: relative;
  }
  h1 {
    font-size: 3rem;
  }
 
  .primary {
    background-color: rgb(249, 87, 89);
    color: white;
    border-radius: 6.5rem;
    border: none;
    padding: 0.75rem 4rem;
    font-size: 1rem;
    margin-top: 1rem;
    cursor: pointer;
  }

  .cards-container {
    display: flex;
    margin-top: 3rem;
    flex-wrap: wrap;
  }

  .card {
    background-color: rgb(27, 60, 138);
    width: 28%;
    color: white;
    border-radius: 1rem;
    padding: 1rem;
    margin-right: .5rem;
    margin-bottom: 1rem;
    position: relative;
  }

  .card p {
    position: absolute;
    top: -30%;
    left: 92.5%;
    color: rgba(255, 255, 255, .178);
  }
  /* 205 */
</style>

