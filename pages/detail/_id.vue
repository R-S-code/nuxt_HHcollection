<template>
  <main>
    <DetailTitle/>
    <div v-if="state.character_info" class="char-prof">
      <img :src="`http://localhost:1337` + state.character_info.character_img.url" alt="キャラクター画像">
      <div class="char-prof__info">
        <div>
          <p><span>・</span>名前</p>
          <p>{{ state.character_info["name"] }}</p>
          <p></p>
        </div>
        <div>
          <p><span>・</span>性別</p>
          <p>{{ state.character_info["gender"] }}</p>
        </div>
        <div>
          <p><span>・</span>念系統</p>
          <p>{{ state.character_info["ability_type"] }}</p>
        </div>
        <div>
          <p><span>・</span>紹介</p>
          <p>{{ state.character_info["introduce"] }}</p>
        </div>
      </div>
    </div>
    <DetailTopBtn />
  </main>
</template>

<script lang="ts">
  import { reactive, onBeforeMount, useContext } from '@nuxtjs/composition-api'
  import axios from 'axios';

  export default {
    setup() {
      const state = reactive({
        character_info:null,
      })

      const { route } = useContext()

      const getCharacterInfo = async ()=> {
        state.character_info = await axios.get("http://localhost:1337/characters/" + route.value.params.id)
        state.character_info = state.character_info.data
        console.log(state.character_info)
      }

      onBeforeMount(() => {
        getCharacterInfo()
      })

      return{
        state
      }
    },
  }
</script>


<style lang="scss" scoped>
  .char-prof {
    align-items: center;
    border: 2px solid $border-gray;
    display: flex;
    margin-top: 5rem;
    padding: 1.5rem;
    img {
      &:first-child {
        height: 40rem;
        width: 40rem;
      }
    }
    &__info {
      font-weight: 700;
      margin-left: 2rem;
      width: 100%;
      div {
        display: flex;
        border-bottom: 2px solid $border-gray;
        p {
          padding: 2.5rem 0 1rem;
          span {
            color: $brown;
          }
          &:first-child {
            margin-right: 2rem;
            white-space: nowrap;
            width: 7rem;
          }
          &:last-child {
            flex: 1;
          }
        }
        &:last-child {
          border: none;
        }
      }
    }
  }
</style>
