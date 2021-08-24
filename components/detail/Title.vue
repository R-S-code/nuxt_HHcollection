<template>
  <div class="title">
    <div>
      <h1>Profile</h1>
      <h1>プロファイル</h1>
    </div>
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
  }
</style>

