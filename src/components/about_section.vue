<template>
  <section class="about" id="about">
    <div class="about__gradient"></div>
    <div class="about__gradient2"></div>
    <div class="container">
      <div class="about__wrap">
        <div class="about__img_wrap">
          <img class="about__img" src="~@/assets/images/cube.png" alt="cube" />
        </div>
        <h2 class="about__title title">About AIR Collab</h2>
        <p class="about__subtitle subtitle">
          Collaborate with brilliant like-minded creators and gain some new fans
        </p>
        <button type="button" class="about__btn btn">Start Collab</button>
      </div>
    </div>
  </section>
</template>


<style lang="scss">
.about {
  padding: 150px 0 200px;
  overflow-x: hidden;
  position: relative;
  @media screen and (max-width: 768px) {
    padding: 100px 0;
  }
}
.about__gradient {
  width: 15%;
  height: 40%;
  position: absolute;
  left: -4%;
  bottom: 40%;
  z-index: 10;
  transform: translateY(50%);
  background-blend-mode: overlay;
  filter: blur(50px);
  border-radius: 50px 169px 176px 50px / 25px 72px 61px 25px;
  animation: gradient 6s ease infinite;
  background-image: linear-gradient(
    180deg,
    rgba(70, 50, 153, 1) 0%,
    rgba(69, 48, 150, 0.40129555240064774) 100%
  );
}
.about__gradient2 {
  width: 15%;
  height: 40%;
  position: absolute;
  right: -4%;
  bottom: 27%;
  z-index: 10;
  transform: translateY(50%);
  background-blend-mode: overlay;
  filter: blur(50px);
  border-radius: 310px 0px 0px 68px / 150px 0px 0px 34px;
  background-image: linear-gradient(
    180deg,
    rgb(35, 24, 77) 0%,
    rgba(29, 18, 75, 0.401) 100%
  );
}
.about__img_wrap {
  margin-bottom: 30px;

  img {
    width: 10%;
    @media screen and (max-width: 768px) {
      width: 15%;
    }
  }
}
.about__wrap {
  text-align: center;
}
</style>