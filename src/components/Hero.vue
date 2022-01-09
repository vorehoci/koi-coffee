<script setup lang="ts">
</script>

<template>
  <div class="hero-container">
    <transition name="hero-animation" :duration="5000" appear>
      <video class="hero-koi" loop autoplay muted>
        <source src="./../assets/koi-video.mp4" alt="Koi fish video"/>
      </video>
    </transition>
    <div class="hero-content">
      <transition name="fade" appear>
        <h1 class="hero-title">Welcome to <br> Koi Coffee</h1>
      </transition>
      <transition name="fade" appear>
        <div class="hero-description">
          <p class="hero-description__paragraph">Organically grow the holistic world view of disruptive innovation via workplace diversity and empowerment.</p>
          <p class="hero-description__paragraph -accent">Dont question it!</p>
          <button class="hero-signup">SIGN UP NOW!</button>
        </div>
      </transition>
    </div>
  </div>
</template>

<style scoped>
.hero-container {
  height: 100vh;
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
}

.fade-enter-active {
  transition: 0.5s ease;
}

.fade-enter-from {
  opacity: 0;
  margin-left: -25px;
}

.hero-title {
  transition: 0.5s ease;
  transition-delay: 2s;
  margin-top: 0;
  margin-bottom: 0;
  color: #ff5d8e;
  letter-spacing: 3px;
  font-size: 100px;
  animation: 0.3s text-shadow-animation ease-in forwards;
  animation-delay: 3s;
}


@keyframes text-shadow-animation {
  0% {
    text-shadow: 0px 0px #f6ff00, 0px 0px #9c9bff;
  }
  100% {
    text-shadow: 4px 4px #f6ff00, 8px 8px #9c9bff;
  }
}

.hero-koi {
  border-radius: 10px;
  overflow: hidden;
  width: auto;
  z-index: -1;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  filter: grayscale(1);
  opacity: 0.2;
  pointer-events: none;
  height: 80%;
}

.hero-description {
  transition-delay: 4s;
}

.hero-title + .hero-description { 
  margin-top: 40px;
}

.hero-description__paragraph {
  margin: 0;
  line-height: 30px;
  font-size: 24px;
}

.hero-description__paragraph.-accent {
  font-weight: bold;
}

.hero-description__paragraph + .hero-description__paragraph {
  margin-top: 10px;
}

.hero-description__paragraph + .hero-signup {
  margin-top: 30px;
}
.hero-signup {
  position: relative;
  border: 0;
  padding: 20px 40px;
  color: white;
  background: #9c9bff;
  font-size: 18px;
  font-weight: bold;
  transition: 0.3s;
  cursor: pointer;
  border-radius: 5px;
}

.hero-signup:hover {
  background: #ff5d8e;
}

.hero-content {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}

.hero-animation-enter-active {
  animation: hero-animation 2s linear;
}

@keyframes hero-animation {
  0% {
    opacity: 0;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0.2;
  }
}

</style>
