<template>
  <header class="header">
    <i class="material-icons icon">menu</i>
    <div>
      <i class="material-icons icon">search</i>
      <img class="account-img" src="/img/account.png" alt="account" />
      <i class="material-icons icon">shopping_cart</i>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  background-color: black;
  padding: 0.4rem 0.7rem;
  width: 100%;

  .icon {
    font-size: 2.2rem;
    color: white;
  }

  .account-img {
    margin: 0 0.2rem;
    padding: 0.2rem;
    height: 2.2rem;
  }
}
</style>
