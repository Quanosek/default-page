<script setup lang="ts">
const host = window.location.host;
</script>

<template>
  <main>
    <div class="text-overlay">
      <h1>
        Strona
        <span>{{ host }}</span>
        nie istnieje
      </h1>

      <p>Upewnij się, że wpisana nazwa jest poprawna</p>
    </div>

    <div class="background-image" />

    <a class="domain" href="https://www.klalo.pl/"> domena klalo.pl</a>
  </main>

  <footer>
    <p>
      Stworzone i utrzymywane przez
      <a href="https://github.com/Quanosek">Jakuba Kłało</a>
    </p>

    <p>Wszelkie prawa zastrzeżone &#169; 2023</p>
  </footer>
</template>

<style scoped lang="scss">
.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: url("./assets/wallpaper.webp") no-repeat center center;
  background-size: cover;
  animation: animation 200s infinite alternate;
  filter: blur(2px);

  @keyframes animation {
    0% {
      transform: scale(1.8) rotate(0deg);
    }
    100% {
      transform: scale(1.6) rotate(35deg);
    }
  }
}

.text-overlay {
  z-index: 1;
  padding: 1.5% 2%;
  width: 100%;
  position: relative;
  bottom: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: rgba(#000000, 0.45);
  font-size: 125%;

  span {
    user-select: text;
    text-decoration: underline;
    cursor: text;
  }
}

.text-overlay,
.domain {
  text-shadow: 2px 2px 4px rgba(#000000, 0.8);
}

.domain {
  position: relative;
  text-decoration: none;
}

@media (max-width: 768px) {
  .text-overlay {
    bottom: 8vw;
    padding: min(1rem, 5%) 2%;
    font-size: min(5vw, 110%);
  }

  .domain {
    bottom: 3vw;
    font-size: min(4vw, 100%);
  }
}
</style>
