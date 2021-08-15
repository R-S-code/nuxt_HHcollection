<template>
  <div class="title">
    <div>
      <h1>Character</h1>
      <h1>キャラクター</h1>
    </div>
    <img src="@/assets/img/title_Gon.png" alt="キャラクター画像">
  </div>
</template>

<style lang="scss" scoped>
  .title {
    margin-top: 9rem;
    position: relative;
    div {
      h1 {
        color: $green;
        &:first-child {
          font-size: 5rem;
          font-weight: bold;
        }
        &:last-child {
          background-color: $sub-title-gray;
          border-radius: 2rem;
          font-size: 2rem;
          padding-left: 1rem;
        }
      }
    }
    img {
      bottom: 0;
      display: block;
      position: absolute;
      right: 0;
      width: 11.5rem;
    }
  }
</style>

