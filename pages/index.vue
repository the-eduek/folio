<template>
  <section class="hero">
    <div class="hero__image">
      <img src="~/assets/images/hero5.svg" alt="man standing">
    </div>

    <article class="hero__text">
      
      <h1>
        <span>Hello!</span>
        <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /> 
        </svg>
      </h1>
      <p>I'm <span>Eduek Akpan-Nyah</span>, a <span>Frontend Developer</span> based in <span>Lagos, Nigeria</span>.</p>
      <p>I like to craft digital solutions to real world problems by building solid, scalable web products with intuitive user experiences.</p>
      <div class="cta">
        <NuxtLink to="/projects" class="btn">
          <div>🔭 Explore Projects
            <b>
              <span>&rarr;</span>
              <span>&rarr;</span>
            </b>
          </div>
        </NuxtLink>
        <Button text="📥 Download Résumé" link="  Eduek Akpan-Nyah.pdf" download="Eduek Akpan-Nyah"/>
      </div>
    </article>    
    <Underline/>
    <Contact/>
    <Underline/>
    <Footer/>
  </section>
</template>

<script>
</script>

<style lang="scss" scoped>
  @import "~/assets/styles/pages/index.scss";
</style>