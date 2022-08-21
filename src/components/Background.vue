<template>
  <div class="">
    <img class="bg-image" src="@/assets/Coding-Challenge-Image.png" alt="Trees">
    <div class="bg-strip"></div>
  </div>
</template>


<style lang="scss">
    $base-color: #611818;

    .bg-strip {
        background-color: $base-color;
        position: absolute;
        top: 0;
        width:413px;
        height: 100vh;
    }

    .bg-image {
        position: absolute;
        width: 100vw;
        height: 100vh;

    }
    @media (max-width:1000px) {
        .bg-strip {
            width: 100vw;
            height: 100%;
            top: 0;
            z-index: -1;

        }

        .bg-image {
            width: 100vw;
            height: auto;
            
        }
    }
</style>