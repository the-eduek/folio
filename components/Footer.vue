<template>
  <footer>
    <div>
      <p>🚀</p>
      <h2>Drop me a line or two &ndash;</h2>
    </div>

    <ul>
      <li>
        <a href="mailto:eduekakpannyah@gmail.com">
          <span>eduekakpannyah@gmail.com</span>
          <span>eduekakpannyah@gmail.com</span>
        </a>
      </li>
      <li>
        <a href="https://wa.me/+2348166647688" target="_blank" rel="noopener noreferrer">
          <span>wa.me/eduek</span>
          <span>wa.me/eduek</span>        
        </a>
      </li>
      <li>
        <a href="https://t.me/eduek" target="_blank" rel="noopener noreferrer">
          <span>t.me/eduek</span>
          <span>t.me/eduek</span> 
        </a>
      </li>
    </ul>

    <p>&copy; 2021 • Eduek Akpan-Nyah</p>
  </footer>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "~/assets/styles/variables";
@import "~/assets/styles/mixins";

footer {
  padding: 3rem 0;
  text-align: right;
  > div {
    margin-bottom: 2rem;
    p {
      font-size: 1.5rem;
      margin-right: 0.5rem;
      display: inline;
    }

    h2 {
      display: inline;
    }
  }

  ul {
    li {
      height: 24px;
      list-style: none;
    }
  }

  > p {
    margin: 2rem 0;
    font-size: 14px;
  }  
}

@media screen and (min-width: 768px) {
  footer {
    padding: 3.5rem 0;
    ul {
      margin: 3.5rem 0;
    }
  }
}
</style>