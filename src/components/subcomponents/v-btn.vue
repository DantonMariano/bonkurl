<template>
  <div class="v-btn">
      <button>Default</button>
  </div>
</template>

<style lang="scss" scoped>
.v-btn{
    position: absolute;
    right: 0;
    top: 0;
    margin: .2rem -1rem;
    width: 100%;
    height: 100%;
    button{
        cursor: pointer;
        padding: .48rem 1rem;
        outline: none;
        border: none;
        border-radius: 0px 15px 15px 0;
        // box-shadow: 0 2px 4px 2px rgba(0, 0, 0, 0.2);
        text-transform: to-upper-case($string: "");
    }
}
</style>