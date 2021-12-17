<template>
  <header>
    <nav :class="{'nav--open': isNavOpen}">
      <ul>
        <li @click="closeNav"><NuxtLink to="/"><span>Home</span><span>Home</span></NuxtLink></li>
        <li @click="closeNav"><NuxtLink to="/about"><span>About</span><span>About</span></NuxtLink></li>
        <li @click="closeNav"><NuxtLink to="/projects"><span>Projects</span><span>Projects</span></NuxtLink></li>
        <li @click="closeNav"><a href="/Eduek Akpan-Nyah.pdf" target="_blank" download="Eduek Akpan-Nyah"><span>Résumé</span><span>Résumé</span></a></li>
      </ul>
    </nav>

    <div class="hamburger" :class="{'hamburger--close': isNavOpen}" @click="navToggle">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
      isNavOpen: false
    }
  },
  methods: {
    navToggle() {
      this.isNavOpen = !this.isNavOpen
    },
    closeNav() {
      setTimeout(() => {
        this.isNavOpen = !this.isNavOpen
      }, 350)
      
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/styles/variables";
@import "~/assets/styles/mixins";

header {
  padding: 2.5rem 0;
  nav {
    height: 100vh;
    width: 100vw;
    position: fixed;
    z-index: 3;
    top: 0;
    left: -100vw;
    background-color: #fff;
    transition: 250ms ease-out;
    ul {
      background-color: rgba($color: $primary, $alpha: 0.05);
      list-style: none;
      height: 100%;
      width: 100%;
      li {
        padding: 1rem;
        width: fit-content;
        text-transform: uppercase;
        &:first-child{
          padding-top: 1.5rem;
        }

        a {
          padding: 5px;
          height: 30px;
          color: $dark;
          span {
            padding-bottom: 1.5rem;
          }
        }
      }
    }
  }

  nav.nav--open {
    left: 0%;
  }

  .hamburger {
    position: fixed;
    padding: 10px;
    right: 1rem;
    top: 1.5rem;
    z-index: 3;
    > span {
      display: block;
      background-color: $primary;
      border-radius: 1rem;
      width: 1.5rem;
      height: 0.25rem;
      z-index: 3;
      &:nth-child(2) {
        transform: translateX(-4px);
        margin: 0.2rem 0;
      }
    }
  }

  .hamburger--close {
    > span {
      transition: 200ms ease-out;
      &:first-child {
        position: relative;
        top: 0.25rem;
        transform: rotate(-45deg);
      }

      &:nth-child(2) {
        display: none;
      }

      &:last-child {
        transform: rotate(45deg);
      }
    }
  }
}

@media screen and (min-width: 414px) {
  header {
    nav {
    
    ul {
      li {
        padding: 1rem;
        padding-left: 2rem;
        &:first-child{
          padding-top: 2rem;
        }
      }
    }
  }
    .hamburger {      
      right: 1.5rem;
      top: 2rem;
    }
  }
}

@media screen and (min-width: 1024px) {
  header {
    position: fixed;
    padding: 2.5rem 0;
    padding-right: 2.5rem;
    z-index: 3;
    top: 0;
    right: 0;
    width: 100%;
    background-color: #fff;
    nav {
      @include flex(flex-end);
      position: static;
      height: auto;
      width: 100%;
      > ul {
        display: flex;
        background: none;
        width: fit-content;
        li {
          padding: 0 1.25rem;
          &:first-child{
            padding: 0 1.25rem;
          }
        }
      }
    }

    .hamburger {
      display: none;
    }
  } 
}
</style>