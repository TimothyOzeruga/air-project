<template>
  <section class="collab" id="collab">
    <div class="collab__gradient1"></div>
    <div class="collab__gradient2"></div>
    <div class="container">
      <div class="collab__wrap">
        <div class="collab__info">
          <h1 class="collab__title title">
            Collaborate with like-minded creators
          </h1>
          <p class="collab__subtitle subtitle">
            Looking for collaborations that attract new audiences and ensure
            audience retention? We will find matches for you
          </p>
          <button type="button" class="collab__btn">
            Find Brilliant Collab
          </button>
        </div>
        <div class="collab__imgs">
          <img
            class="collab__img1"
            src="~@/assets/images/people.png"
            alt="people"
          />
          <img
            class="collab__img2"
            src="~@/assets/images/people2.png"
            alt="people2"
          />
        </div>
      </div>
    </div>
  </section>
</template>


<style lang="scss">
/* Section Collab */

.collab {
  padding: 150px 0 200px;
  position: relative;
  overflow-x: hidden;
  @media screen and (max-width: 768px) {
    padding: 100px 0;
  }
}
.collab__gradient2 {
  width: 12%;
  height: 25%;
  position: absolute;
  right: -4%;
  bottom: 26%;
  z-index: 10;
  transform: translateY(50%);
  background-blend-mode: overlay;
  filter: blur(50px);
  animation: gradient 5s ease infinite;
  background-image: linear-gradient(
    180deg,
    rgba(70, 50, 153, 1) 0%,
    rgba(69, 48, 150, 0.40129555240064774) 100%
  );
}
.collab__gradient1 {
  width: 12%;
  height: 15%;
  position: absolute;
  right: -4%;
  bottom: 36%;
  z-index: 11;
  transform: translateY(50%);
  background-blend-mode: overlay;
  filter: blur(50px);
  animation: gradient 5s ease infinite;
  background-image: linear-gradient(
    3deg,
    rgba(73, 53, 159, 1) 0%,
    rgba(95, 163, 242, 1) 50%,
    rgba(59, 172, 55, 1) 100%
  );
}

@keyframes gradient {
  0% {
    box-shadow: 0 -200px 100px -100px rgb(73, 53, 159) inset;
  }
  50% {
    box-shadow: 0 -200px 100px -100px rgb(25, 99, 23) inset;
  }
  100% {
    box-shadow: 0 -200px 100px -100px rgb(73, 53, 159) inset;
  }
}

.collab__wrap {
  display: flex;
  justify-content: space-between;
  gap: 30px;
}

.collab__info {
  padding-top: 40px;
  width: 60%;
  @media screen and (max-width: 940px) {
    width: 100%;
  }
  @media screen and (max-width: 500px) {
    text-align: center;
  }
}
.collab__btn {
  font-family: "Gilroy";
  font-size: 16px;
  font-weight: 700;
  text-transform: uppercase;
  border: none;
  border-radius: 6px;
  padding: 15px 30px;
  background-color: #baf11f;
  outline: none;

  &:hover {
    background-color: #ceff43;
  }
  &:active {
    background-color: #b1e41e;
  }
}
.collab__imgs {
  position: relative;
  width: 40%;
  .collab__img1 {
    width: 100%;
    animation: fadeInUp 2s ease-in-out;
  }
  .collab__img2 {
    position: absolute;
    left: 0;
    top: -4px;
    width: 100%;
    animation: fadeInUp 3s ease-in-out;
  }
  @media screen and (max-width: 940px) {
    display: none;
  }
}
</style>