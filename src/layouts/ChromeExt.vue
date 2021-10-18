<template>
    <div class="ChromeExt">
        <Bonk></Bonk>
    </div>
</template>

<script>
import Bonk from "../components/Bonk.vue";
export default {
    name: "ChromeExt",
    components: {
        Bonk,
    }
}
</script>

<style lang="scss">
// font-family: 'Patrick Hand', cursive;
@import url('https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap');
.ChromeExt{

    width: 16rem;
    border: 1px solid;
    background: #EFDCAC;
    color: #555554;
    font-family: 'Patrick Hand', cursive;
    font-size: 18px;
}
</style>