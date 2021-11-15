<template>
  <div class="loader">
    <div class="text">{{ label }}</div>
    <img src="https://upload.wikimedia.org/wikipedia/commons/2/26/Spotify_logo_with_text.svg" alt="">
    <div class="text">Loading...</div>
  </div>
</template>

<script>
export default {
  name: "Loader",
  props: ["label"],
};
</script>

<style scoped lang="scss">

.loader {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background: white;
}
img {
  width: 50%;
  margin: 1rem 0;
  animation: pulse 2s infinite alternate;
}
@keyframes pulse {
  from {
    transform: scale(1);
  }
  to {
    transform: scale(1.2);
  }
}
.text {
  text-transform: uppercase;
  letter-spacing: 2px;
}
</style>