<template>
  <div>
    <div ref="cursorInner" class="cursorInner"></div>
    <div ref="cursorOuter" class="cursorOuter"></div>
    <Nav/>
    <Nuxt/>
    <Socials/>
  </div>
</template>

<script>
export default {
  mounted() {
    const cursorInner = this.$refs.cursorInner;
    const cursorOuter = this.$refs.cursorOuter;

    document.addEventListener("mousemove", e => {
      cursorInner.setAttribute(
        "style", `top: ${e.pageY}px; left: ${e.pageX}px;`
      );
      cursorOuter.setAttribute(
        "style", `top: ${e.pageY - 15}px; left: ${e.pageX - 15}px;`
      );
    });

    document.addEventListener("click", e => {
      cursorInner.classList.add('clicked');

      setTimeout(() => {
        cursorInner.classList.remove('clicked');
      }, 350)
    });
  }
}

</script>

<style lang="scss" scoped>
@import "~/assets/styles/variables";

@keyframes cursorAnimation {
  from {
    transform: scale(1.4);
  }

  to {
    transform: scale(1.1);
  }
}

@keyframes cursorAnimation2 {
  from {
    transform: scale(1.15);
  }

  to {
    transform: scale(1.3);
  }
}

@keyframes cursorAnimation3 {
  0% {
    transform: scale(4);
  }

  50% {
    transform: scale(6.5);
  }
  
  100% {
    transform: scale(9);
    opacity: 0;
  }
}

@media screen and (min-width: 768px) {
  .cursorInner {
    pointer-events: none;
    overflow: hidden;
    display: block;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: $primary;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 20;
    transform: translate3d(-50%, -50%, 0);
    animation: cursorAnimation ease-out 500ms infinite alternate;
  }

  .cursorOuter {
    @extend .cursorInner;
    width: 40px;
    height: 40px;
    background: rgba($color: $gray, $alpha: 0.1);
    border: 1px solid rgba($color: $dark, $alpha: 0.2);
    transition: 300ms ease-out;
    mix-blend-mode: normal;
    animation: cursorAnimation2 ease-out 750ms infinite alternate;
  }

  .clicked {
    border: 3px solid rgba($color: $primary, $alpha: 0.8);
    background-color: rgba($color: $gray, $alpha: 0.1);  
    animation: cursorAnimation3 ease-out 300ms forwards;
  }
}
</style>