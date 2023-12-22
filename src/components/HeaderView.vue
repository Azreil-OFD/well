<script setup lang="ts">
const emit = defineEmits(['target'])

const scrollIntoView = (argv) => {
  return argv
}

</script>

<template>
    <section id="section1">
      <div class="image"></div>
      <header>
        <a href="#section1" id="logo"><img src="@/assets/logo.png" alt="" /></a>

        <ul id="menu">
          <li><a href="#" @click="emit('target' , 2)">О клубе</a></li>
          <li><a href="#" @click="emit('target' , 3)">Как нас найти</a></li>
          <li><a href="#" @click="emit('target' , 4)">Прайс</a></li>
          <li><a href="#" @click="emit('target' , 5)">Галерея</a></li>
        </ul>

        <button id="button">Забронировать</button>
      </header>
      <main>
        <div class="title">
          <span class="title__top">Да, это новый клуб</span>
          <span class="title__bottom">
            <div class="blue">В нефтеюганске</div>
          </span>
        </div>
        <div class="subtitle">
          Неважно сколько вам лет <br />
          и во что вы играете -
          <span class="blue">найдеться все.</span>
        </div>
        <button id="title__button">Забронировать</button>

        <div class="info">
          <div class="internet__speed">
            <img src="@/assets/roket.png" alt="" />
            <span>
              <span class="internet__speed__right">
                Скорость интернета в клубе</span
              >
              <span class="internet__speed__left">
                до
                <div class="blue">1000 мбит/сек</div>
              </span></span>
          </div>
          <div class="devices_list">
            <div class="blue">
              <div class="device">PC</div>
              <div class="device">XBOX</div>
              <div class="device">PS5</div>
              <div class="device">VR</div>
              <div class="device">Настольные игры</div>
            </div>
          </div>
        </div>
        <div class="arrow">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </main>
    </section>
</template>

<style scoped>

#section1 .image {
  padding: 0;
  margin: 0;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 1;
  height: 100vh;
  width: 100%;
  background: url("@/assets/Header.png") center/cover no-repeat;
  z-index: -100;
}

/* Первая секция */
header {
  padding: 10px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
}

#logo {
  color: white;
  text-decoration: none;
  font-size: 1.5em;
}

#menu {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  font-size: 16px;
}

#menu li {
  margin: 0 15px;
}

#menu a {
  color: white;
  text-decoration: none;
}

#button {
  border: none;
  border-radius: 10px;
  cursor: pointer;
  background-color: rgb(0, 120, 255);
  text-align: center;
  padding: 10px 20px;
  color: aliceblue;
}
main {
  display: flex;
  flex-direction: column;
  align-items: start;
}
.title {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding-top: 15vh;
  font-size: 6vh;
  text-align: start;
  font-weight: bold;
}

.subtitle {
  display: flex;
  flex-direction: column;
  padding-top: 4vh;
  font-size: medium;
  font-weight: bold;
  text-align: start;
  opacity: 0.9;
}

#title__button {
  margin-top: 6vh;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  background-color: rgb(0, 120, 255);
  text-align: center;
  font-size: 2vh;
  padding: 15px 30px;
  color: aliceblue;
  box-shadow: 0 0 30px 0 #3195d7, inset 0 0 30px 0 rgba(244, 244, 244, 0.509);
  font-weight: bold;
}

.info {
  margin-top: 20vh;
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
}
.info span {
  text-align: start;
}

.devices_list {
  display: flex;
  font-size: 2.7vh;
  justify-content: center;
  font-weight: bold;
  gap: 3vh;
}

.internet__speed {
  font-size: 3vh;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 2vh;
}
.internet__speed__left {
  display: flex;
  flex-direction: row;
}

.arrow {
  margin: 40px auto 10px auto;
  width: 38px;
  height: 100px;
}
.arrow span {
  display: block;
  width: 20px;
  height: 20px;
  border-bottom: 5px solid #337ab7;
  border-right: 5px solid #337ab7;
  transform: rotate(45deg);
  margin: -16px 0;
  animation: arrow 2s infinite;
}
.arrow span:nth-child(2) {
  animation-delay: -0.2s;
}
.arrow span:nth-child(3) {
  animation-delay: -0.4s;
}
@keyframes arrow {
  0% {
    opacity: 0;
    transform: translate(0, -20px) rotate(45deg);
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    transform: translate(0, 20px) rotate(45deg);
  }
}

@media (max-width: 1200px) {
  section {
    padding: 0 10vh;
  }
  #section1 .image {
    background-position: 70% center;
  }
}
@media (max-width: 1000px) {
  #menu {
    display: none;
  }
}

@media (max-width: 768px) {
  #section1 {
    height: 93vh;
  }
  #section1 .image {
    height: 93vh;
  }
  header {
    margin-top: 2vh;
  }
  .title {
    margin-top: 5vh;
  }
  #logo img {
    height: 3.2vh;
  }

  section {
    padding: 0 2vh;
  }

  #section1 .image {
    opacity: 0.3;
    background-position: 70% center;
  }
  .title {
    font-size: 4.5vh;
  }
  .subtitle {
    font-size: 2vh;
  }

  .info {
    margin-top: 7vh;
    flex-direction: column-reverse;
    gap: 3vh;
  }

  .devices_list {
    font-size: 1.9vh;
  }

  .internet__speed {
    font-size: 2vh;
  }
  .internet__speed__left {
    display: flex;
    flex-direction: row;
  }
}
</style>
