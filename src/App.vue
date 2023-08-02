<script setup lang="ts">
const host = window.location.host;
</script>

<template>
  <main>
    <div class="container">
      <div class="text">
        <h1>
          Strona
          <span>{{ host }}</span>
          nie istnieje
        </h1>

        <p>Upewnij się, że wpisana nazwa jest poprawna</p>
      </div>

      <a class="domain" href="https://www.klalo.pl/"> domena klalo.pl</a>
    </div>

    <div class="background-image" />
  </main>

  <footer>
    <div className="responsive-holder">
      <p>
        Stworzone z <span>💙</span> przez
        <a href="https://github.com/Quanosek">Jakuba Kłało</a>
      </p>

      <p>Wszelkie prawa zastrzeżone &#169; 2023</p>
    </div>
  </footer>
</template>

<style scoped lang="scss">
.container {
  z-index: 1;
  width: 100%;
  position: relative;
  bottom: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1.5rem;
  font-size: 125%;
  text-align: center;

  span {
    user-select: text;
    text-decoration: underline;
    cursor: text;
  }
}

.text {
  padding: 2rem 3%;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  background-color: rgba(#000000, 0.45);
}

.domain {
  padding: 5px 20px;
  border-radius: 0.4rem;
}

@media (max-width: 768px) {
  .container {
    bottom: 5vw;
    font-size: min(110%, 3.5vw);
    gap: min(1.6rem, 5vw);
  }

  .text {
    padding: min(2rem, 5vw) 5%;
    gap: min(0.65rem, 2vw);
  }
}

.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

  background-image: url("./assets/wallpaper.webp");
  background-size: cover;
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-position: center;
  background-blend-mode: multiply;

  animation: animation 180s infinite alternate;
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
</style>
