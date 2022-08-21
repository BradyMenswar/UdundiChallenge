<template>
    <div class="social-bar">
        <button><img src="@/assets/Facebook.svg" alt="facebook link"></button>
        <button><img src="@/assets/Instagram.svg" alt="instagram link"></button>
    </div>
</template>

<style lang="scss">
    .social-bar {
        position: absolute;
        bottom: 2rem;
        gap: 1rem;
        right: 1rem;
        display: flex;
        flex-direction: column;
        
        button {
            background: none;
            border: none;
        }
    }

     @media (max-width: 1000px) {

            .social-bar {
                flex-direction: row;
                gap: 10px;
                left: calc(50% - 50px);
                bottom: 1rem;

                button >img {
                    width: 40px;
                    height: 40px;
                }
            }
        }

</style>