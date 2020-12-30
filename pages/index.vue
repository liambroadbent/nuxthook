<template>
  <div class="container">
    <div>
      <h1 class="title">
        nuxthook
      </h1>

      <h2 class="subtitle">
        {{ ip.data.amount }}
      </h2>
    </div>
  </div>
</template>

<script>
export default {
async asyncData({ $axios }) {
  const ip = await $axios.$get('https://api.coinbase.com/v2/prices/spot?currency=USD')
  return { ip }
}

}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
