<template>
  <section class="contact">
    <h2>Need a developer?</h2>
    <p>Reach out through
      <a :href="mailLink">
        <span>eduekakpannyah@gmail.com</span>
        <span>eduekakpannyah@gmail.com</span>
      </a>
    </p>

    <Button :link="mailLink" text="Reach out through">
      <template>
        <span>eduekakpannyah@gmail.com</span>
      </template>
    </Button>
  </section>
</template>

<script>
export default {
  data () {
    return {
      mailLink: "mailto:eduekakpannyah@gmail.com"
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/styles/variables";
@import "~/assets/styles/mixins";

section.contact {
  padding: 3rem 0;
  text-align: center;
  p {
    a {
      color: $primary;
    }
  }
  
  a.btn {
    display: none;
  }
}

@media screen and (min-width: 460px) {
  section.contact {
    p {
      @include flex;
      > a {
        top: 1px;
        border-bottom: 1px solid rgba($color: $primary, $alpha: 0.75);
        padding-left: 3px;
        padding-bottom: 3px;
      }
    }
  }
}

@media screen and (min-width: 700px) {
  section.contact {
    p {
      display: none;
    }

    a.btn {
      display: block;
      span {
        color: $primary;
        font-weight: 600;
        padding: 0 2px;
      }
    }
  }  
}

@media screen and (min-width: 768px) {
  section.contact {
    padding: 3.5rem 0;

     a.btn {
      margin-top: 3rem
    }
  }
}
</style>