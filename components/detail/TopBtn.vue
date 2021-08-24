<template>
  <div class="top-btn">
    <NuxtLink to="/">
      <button>キャラクターリストに戻る</button>
    </NuxtLink>
  </div>
</template>

<style lang="scss" scoped>
  .top-btn {
    display: flex;
    justify-content: center;
    a {
      cursor: pointer;
      display: flex;
      justify-content: center;
      margin: 13.5rem 0 21rem;
      transition: 0.1s;
      button {
        background-color: $brown;
        border-radius: 2rem;
        color: white;
        font-size: 2rem;
        font-weight: 700;
        margin: 0 auto;
        padding: 2.5rem 5rem;
      }
      &:hover {
        opacity: 0.6;
      }
    }
  }
</style>
