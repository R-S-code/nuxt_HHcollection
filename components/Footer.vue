<template>
  <footer>
    <div>
      <img src="@/assets/img/logo.png" alt="HunterHunter">
      <p>ハンターハンターキャラクターハンターハンターキャラクター</p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
  @font-face {
    font-family: "Hunter";
    src: url("@/assets/font/hunter.ttf");
  }

  footer {
    background-color: $brown;
    height: 10.5rem;
    padding: 1.5rem 2.5rem;
    div {
      align-items: center;
      border: 1px solid white;
      display: flex;
      height: 8rem;
      padding: 0.5rem 1.5rem;
        p {
          color: white;
          font-family: "Hunter";
          font-size: 2rem;
          margin-left: auto;
        }
        img {
          display: block;
          width: 16rem;
        }
    }
  }
</style>

