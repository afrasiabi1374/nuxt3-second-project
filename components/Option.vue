<script setup lang="ts">
import { Gender, Popularity, Length } from '@/data';

    interface OptionProps {
        option: {
            title: string;
            category: string;
            buttons: Gender[] | Popularity[] | Length[];
        };
        options: {
            gender: Gender;
            popularity: Popularity;
            length: Length;
        }

    }
    const props = defineProps<OptionProps>()
</script>
<template>
    <div class="option-buttons">
    <h4>{{option.title}}</h4>
        <button
            v-for="value in option.buttons"
            :key="value"
            class="option option-left"
            :class="options[option.category] === value && 'option-active'"
            @click="options[option.category] = value"
        >{{value}}</button>
    </div>
</template>
<style scoped>


  .option-container {
    margin-bottom: 2rem;
  }

  .option {
    background-color: white;
    outline: 0.15rem solid rgba(249, 87, 89);
    border: none;
    padding: .75rem;
    width: 12rem;
    font-size: 1rem;
    color: rgb(27, 60, 138);
    cursor: pointer;
    font-weight: 200;
  }

  .option-left {
    border-radius: 1rem 0 0  1rem;
  }

  .option-right {
    border-radius: 0  1rem  1rem  0;
  }
  .option-active {
    background-color: rgb(249, 87, 89);
    color: white;
  }
</style>