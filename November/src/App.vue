<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import ClickCount from './components/ClickCount.vue'
import InputText from './components/InputText.vue'
import ItemList from './components/ItemList.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="This is Mock Site!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>

  <article>
    <header>
      <h1>下は実装したコンポーネント：</h1>
    </header>
    <section>
      <input-text />
    </section>
    <section>
      <click-count />
    </section>
    <section>
      <item-list />
    </section>
  </article>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
