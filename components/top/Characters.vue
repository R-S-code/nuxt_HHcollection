<template>
  <div class="characters">
    <div  v-for="(character) in state.characters" :key="character.id" class="characters__character">
      <NuxtLink :to="`/detail/` + character.id">
        <img :src="`http://localhost:1337` + character.character_img.url" alt="">
        <div><p>{{ character.name }}</p></div>
      </NuxtLink>
    </div>
  </div>
</template>

<script lang="ts">
  import { reactive,  onMounted } from '@nuxtjs/composition-api'
  import axios from 'axios';

  export default {
    setup() {
      const state = reactive({
        characters:null,
        character_img_url:null,
      })

      const getCharacters = async ()=> {
        state.characters = await axios.get("http://localhost:1337/Characters")
        state.characters = state.characters.data
      }

      onMounted(() => {
        getCharacters()
      })

      return{
        state
      }
    },
  }
</script>

<style scoped lang="scss">
  .characters {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 12rem;
    &__character {
      display: flex;
      height: 28.5rem;
      justify-content: center;
       margin-top: 10rem;
      text-align: center;
      width: 25%;
      a {
        border: 2px solid $border-gray;
        cursor: pointer;
        transition: 0.1s;
        width: 22rem;
        &:hover {
          opacity: 0.6;
        }
        img {
          border: 2px solid $border-gray;
          display: block;
          height: 20rem;
          margin: 1rem auto 0;
          width: 20rem;
        }
        div {
          background-color: $green;
          color: white;
          display: inline-block;
          margin-top: 1.5rem;
          max-width: 16rem;
          padding: 0 1rem;
          transform: skewX(150deg);
          p {
            word-wrap: break-word;
            transform: skewX(-150deg);
          }
        }
      }
    }
  }
  @media screen and (max-width: 1000px) {
    .characters {
      a {
        width: 33.3%;
      }
    }
  }
  @media screen and (max-width: 750px) {
    .characters {
      a {
        width: 50%;

      }
    }
  }
</style>
