<template>
  <header>
    <div>
      <div class="row">
        <a class="right-border" href="https://www.erural.net/" target="_blank">
          <img class="icon" src="../assets/erural.png" alt="E-Rural logo" />
        </a>
        <p>Desafio Video Conferência</p>
      </div>
      <div class="row">
        <div class="right-border">
          
        </div>
        <a
          href="https://github.com/GabrielVita"
          rel="noreferrer noopener"
          target="_blank"
        >
          <img class="icon" :src="github" alt="Github repo" />
        </a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      github: require("../assets/github.svg"),
    };
  },
};
</script>

<style>
header {
  font-size: 12px;
  line-height: 16px;
  font-weight: bold;
  border-bottom: 1px solid #c8d1dc;
  padding: 2px;
  background-color: #fff;
}
header > div {
  max-width: 1200px;
  margin: auto;
  padding: 0 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.icon {
  height: 24px;
}
.row {
  display: flex;
  align-items: center;
}
.right-border {
  padding-right: 16px;
  border-right: 1px solid #c8d1dc;
  margin-right: 16px;
}
.button-link {
  border: 1px solid #c8d1dc;
  border-radius: 8px;
  padding: 7px 16px;
}
@media screen and (max-width: 700px) {
  .button-link {
    display: none;
  }
}
</style>
