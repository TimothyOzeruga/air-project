<template>
  <div id="app">
    <siteHeader></siteHeader>
    <main>
      <collabSection></collabSection>
      <aboutSection></aboutSection>
      <serviceSection></serviceSection>
    </main>
  </div>
</template>

<script>
import siteHeader from "@/components/header.vue";
import collabSection from "@/components/collab_section.vue";
import aboutSection from "@/components/about_section.vue";
import serviceSection from "@/components/service_section.vue";
export default {
  name: "App",
  components: {
    siteHeader,
    collabSection,
    aboutSection,
    serviceSection,
  },
};
</script>

<style lang="scss">
@import url("assets/css/style.scss");

// $maxWidth: 1170;
// @mixin adaptiv-font($pcSize, $mobSize) {
//   $addSize: $pcSize - $mobSize;
//   $maxWidth: $maxWidth - 320;
//   font-size: calc(
//     #{$mobSize + px} + #{$addSize} * ((100vw - 320px) / #{$maxWidth})
//   );
// }

:after,
:before {
  box-sizing: border-box;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background: url("assets/images/Texture.png") #1b1c1f;
  font-family: "Gilroy";
  font-size: 18px;
  color: #fff;
}
.container {
  width: 90%;
  max-width: 1170px;
  margin: 0 auto;
}

.title {
  font-size: 64px;
  font-weight: 600;
  line-height: 76px;
  margin-bottom: 30px;
  @media screen and (max-width: 680px) {
    font-size: 50px;
    line-height: 60px;
  }
  @media screen and (max-width: 680px) {
    font-size: 42px;
    line-height: 50px;
  }
}

.subtitle {
  font-size: 22px;
  font-weight: 500;
  line-height: 35px;
  max-height: 400px;
  overflow-y: auto;
  color: rgb(141, 141, 141);
  margin-bottom: 30px;
  @media screen and (max-width: 680px) {
    font-size: 20px;
    line-height: 30px;
  }
  @media screen and (max-width: 680px) {
    font-size: 16px;
    line-height: 25px;
  }
}
.btn {
  font-family: "Gilroy";
  font-size: 16px;
  font-weight: 700;
  color: #fff;
  text-transform: uppercase;
  border: 3px solid rgb(141, 141, 141);
  border-radius: 6px;
  padding: 12px 50px;
  background-color: transparent;
  outline: none;

  &:hover {
    border: 3px solid #fff;
    background-color: #fff;
    color: #000;
  }
  &:active {
    border: 3px solid #fff;
    color: #fff;
    background-color: #1f2025;
  }
}
main {
  padding-top: 140px;
}
h2,
h1 {
  animation: fadeInUp 2s ease-in-out;
}
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translate3d(0, 100px, 0);
  }
  100% {
    opacity: 1;
    transform: none;
  }
}
</style>
