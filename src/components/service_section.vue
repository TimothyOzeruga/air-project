<template>
  <section class="service" id="section">
    <div class="container">
      <div class="title__wrap">
        <h2 class="collab__title title">Let's look closer how it works</h2>
      </div>
      <div class="service__wrap">
        <div class="services__imgs">
          <img
            :class="{ animation__img: animationImg }"
            class="service__img"
            src="~@/assets/images/faces.png"
            alt="faces"
          />
        </div>
        <div class="service__info">
          <h3 class="service__title">Searching ideal collaboration for you</h3>
          <p class="servise__subtitle subtitle">
            Analyze your niche and its leading creators. Identify leading
            authors with intersecting audiences and themes
          </p>
          <button type="button" class="about__btn btn">
            Find Brilliant Collabs
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      animationImg: false,
    };
  },
  methods: {
    ScrollAnimation() {
      let obj = document.querySelector(".service__img");
      let { top } = obj.getBoundingClientRect();
      if (top < 700) {
        this.animationImg = true;
      }
    },
  },
  created() {
    window.addEventListener("scroll", this.ScrollAnimation);
  },
  unmounted() {
    window.removeEventListener("scroll", this.ScrollAnimation);
  },
};
</script>

<style lang="scss">
.service {
  padding: 150px 0;
  @media screen and (max-width: 768px) {
    padding: 100px 0;
  }
}
.title__wrap {
  text-align: center;
  margin-bottom: 120px;
}
.service__wrap {
  display: flex;
  justify-content: space-between;
  gap: 60px;

  @media screen and (max-width: 980px) {
    flex-direction: row-reverse;
  }
  @media screen and (max-width: 860px) {
    flex-direction: column;
  }
}
.services__imgs {
  width: 50%;
  img {
    width: 100%;
    transform: translateY(50%);
    opacity: 0;
  }
  .animation__img {
    transform: translateX(0);
    opacity: 1;
    transition: all 2s ease;
  }
  @media screen and (max-width: 860px) {
    width: 100%;
    display: flex;
    justify-content: center;
    img {
      width: 80%;
    }
  }
}

.service__info {
  width: 40%;
  display: flex;
  flex-direction: column;
  justify-content: center;

  @media screen and (max-width: 860px) {
    width: 100%;
    text-align: center;
    align-items: center;
  }
}
.service__title {
  font-size: 42px;
  font-weight: 700;
  line-height: 50px;
  margin-bottom: 30px;
  @media screen and (max-width: 680px) {
    font-size: 36px;
    line-height: 45px;
  }
  @media screen and (max-width: 680px) {
    font-size: 32px;
    line-height: 40px;
  }
}
</style>