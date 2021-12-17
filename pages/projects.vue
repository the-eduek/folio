<template>
  <section class="projects">
    <div class="heading">
      <h2>My Projects</h2>
      <p>👨🏽‍💻</p>
      <p>&mdash;</p>
    </div>
    <p>Some of my favorite projects I have built include;</p>
    <div class="project--wrapper">      
      <div class="project">
        <h3>eduek.xyz</h3>
        <p>my portfolio website.</p>

        <div class="project__buttons">
          <Button text="👀 Live" :link="gitLink"/>
          <Button text="🐙 Source Code" :link="gitLink"/>

          <a href="mailto:" subject=""></a>
        </div>
      </div>

      <div class="project">
        <h3>CryptoTracker</h3>
        <p>crypto info web app.</p>

        <div class="project__buttons">
          <Button text="👀 Live" link="https://the-eduek.github.io/cryptotracker/"/>
          <Button text="🐙 Source Code" link="https://github.com/the-eduek/cryptotracker"/>
        </div>
      </div>

      <div class="project">
        <h3>gbalé</h3>
        <p>redesigned homepage of Gbalé.ng.</p>

        <div class="project__buttons">
          <Button text="👀 Live" link="https://gbale.netlify.app/"/>
          <Button text="🐙 Source Code" link="https://github.com/the-eduek/gbale"/>
        </div>
      </div>

      <div class="project">
        <h3>MoviesNextdoor</h3>
        <p>landing page for a movies app.</p>

        <div class="project__buttons">
          <Button text="👀 Live" link="https://the-eduek.github.io/moviesnextdoor/"/>
          <Button text="🐙 Source Code" link="https://github.com/the-eduek/moviesnextdoor"/>
        </div>
      </div>

      <div class="project">
        <h3>bookmark</h3>
        <p>landing page for a browser plugin.</p>

        <div class="project__buttons">
          <Button text="👀 Live" link="https://the-eduek.github.io/bookmark/"/>
          <Button text="🐙 Source Code" link="https://github.com/the-eduek/bookmark"/>
        </div>
      </div>

      <div class="cta">
      <Button text="View More Projects" :link="gitLink"/>
    </div>
    </div>
    <Underline/>
    <Contact/>
    <Underline/>
    <Footer/>
  </section>  
</template>

<script>
export default {
  props: ['text'],
  data() {
    return {
      gitLink: "https://github.com/the-eduek"
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/styles/variables";
@import "~/assets/styles/mixins";

section.projects {
  padding-top: 1rem;
  .project--wrapper {
    display: grid;
    gap: 1.5rem;
    padding: 5px;
    padding-bottom: 1rem;
    .project {
      padding: 1rem;
      border-radius: 1rem;
      border: 1px solid $primary;
      background-color: rgba($color: $primary, $alpha: 0.1);
      h3 {
        color: $dark;
        padding-bottom: 0.5rem;
        border-bottom: 1px solid $primary;
        text-transform: lowercase;
      }

      p {
        font-size: 1.8rem;
        text-transform: lowercase;
      }

      &__buttons {
        a.btn {
          padding: 0.3rem;
          padding-left: 0.8rem;
          &:first-child {
            margin-right: 1rem;
          }
        }  
      }
    }

    .cta {
      @include flex;
      margin: 2rem auto;
    } 
  }
}

@media screen and (min-width: 768px) {
  section.projects {
    .project--wrapper {
      padding: 2rem;      
      padding-bottom: 2.5rem;
      gap: 2.5rem;
      grid-template-columns: repeat(2, minmax(0px, 1fr));
      .project {       
        padding: 2rem;
        margin-bottom: 0;
        height: fit-content;
      }
    }
  }
}

@media screen and (min-width: 1024px) {
  section.projects {
    padding: 1rem;
    padding-top: 4rem;
  }
}
</style>