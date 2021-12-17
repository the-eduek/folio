<template>
  <a :href="link" class="btn">
    <div>
      {{ text }}
      <slot></slot>
      <b>
        <span>&rarr;</span>
        <span>&rarr;</span>
      </b>
    </div>
  </a>
</template>

<script>
export default {
  props: ['link', 'text']
}
</script>

<style lang="scss">
@import "~/assets/styles/variables";
@import "~/assets/styles/mixins";

a.btn {
  padding: 0.75rem;
  padding-left: 1.25rem;
  margin: 0.5rem auto;
  color: $dark;
  border-radius: 2px;
  border: 1px solid $gray;
  background-color: #fff;
  transition: all 200ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
  left: 5px;
  font-weight: 400;
  height: auto;
  overflow: visible;
  &::before {
    height: 100%;
    border-left: 1px solid $gray;
    border-bottom: 1px solid $gray;
    border-bottom-left-radius: 2px;
    top: 5px;
    left: -6px;
    z-index: -1;
    background-color: #fff;
  }

  &:hover {
    color: inherit;
    border-color: $primary;
    span {
      transform: none;
    }

    &::before {
      background-color: $primary;
      border-color: $primary;
      border-radius: 2px;
      height: 100%;
    }
  }

  div {
    @include flex;
    b {
      display: flex;
      width: 33px;
      position: relative;
      z-index: 1;
      overflow-x: hidden;
      span {
        padding: 0 0.5rem;
        transform: translateX(-100%);
        transition: all 250ms ease-in-out;
      }
    }
  }
}
</style>