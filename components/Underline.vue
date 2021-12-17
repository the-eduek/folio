<template>
  <ul>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</template>

<style lang="scss" scoped>
@import "~/assets/styles/mixins";
@import "~/assets/styles/variables";

ul {
  @include flex(space-between);      
  list-style: none;
  li {
    background-color: $gray;
    height: 1px;
    margin: 1rem 0;
    &:first-child {
      width: 57%;
    }

    &:nth-child(2) {
      width: 26%;
    }

    &:nth-child(3) {
      width: 12%;
    }
  }
}

@media screen  and (min-width: 768px){
  ul {
    li {
      &:nth-child(2) {
        width: 29%;
      }
    }
  }
}
</style>