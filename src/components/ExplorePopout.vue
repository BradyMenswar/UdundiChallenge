<template>
<div>   

    <h2 :class="{fadeOut: showPopout}" class="main-text">Explore</h2>
    <button :class="{fadeOut: showPopout}" v-on:click="toggleClicked(); togglePopout();" class="plus-button">

        <img :class="{clicked: click}" src="@/assets/Plus.svg">
        <span>&emsp; More Details</span>
    </button>
    <div class="pop-out" :class="{hidden: !showPopout, closing: showPopout && first}">
        <svg  v-on:click="togglePopout" mlns="http://www.w3.org/2000/svg" width="40" height="40" fill="#611818" class="bi bi-x x" viewBox="0 0 16 16">
            <path d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"/>
        </svg>
        <h3>Explore</h3>

        <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? </p>
        <button>READ MORE</button>
   </div>
</div>
</template>

<script>
    export default {
        data() {
            return {
                showPopout: false,
                click: false,
                first: true
            }
        },

        methods: {
            togglePopout() {
                if(this.showPopout === true) this.click = false;
                this.showPopout = !this.showPopout;
            },

            toggleClicked() {
                this.click = true
            }
        }
    }
</script>

<style lang="scss">


    .main-text {
        clip-path: ellipse(100% 100% at 50% 50%);
        position: absolute;
        left: 187px;
        top: 53%;

        font-family: "Didot"; 
        font-style: normal;
        font-weight: 700;
        font-size: 224px;
        line-height: 289px;
        color: white;

        transition: all 0.65s;
        opacity: 0;

        animation: text-glide 1s forwards;
        animation-delay: 0.45s;

    }

    .plus-button  {
        position: absolute;
        top: 80%;
        left: 187px;
        background: none;
        border: none;

        color: white;
        font-family: 'Lato';
        font-style: normal;
        font-weight: 400;
        font-size: 25px;
        line-height: 30px;
        text-align: center;
        letter-spacing: 0.625px;

        opacity: 0;
        animation: text-glide 1s forwards;
        animation-delay: 0.85s;
        

        span{
            clip-path: ellipse(100% 100% at 50% 50%);
            transition-delay: 0.45s;
        }
    }

    .pop-out {
        transform-origin: 12% 97%;
        transform-box: view-box;
        transform: scale(0.1);
        opacity: 0;

        position: absolute;
        width: 580px;
        height: 702px;
        left: 140px;
        top: 18%;
        padding: 66px 72px;

        background: #FFFFFF;
        box-shadow: 0px 0px 10px 7px rgba(0, 0, 0, 0.296766);

        font-family: 'Lato';
        font-style: normal;
        font-weight: 400;
        font-size: 18px;
        line-height: 22px;
        color: #282828;

        letter-spacing: 0.35px;
        transition: all 0.45s;
        transition-delay: 0.25s;

        clip-path: ellipse(50% 50% at 50% 50%);
        

        * {
            opacity: 0;
            transform: translateX(-100px);
            transition: all 0.35s;

            transition-delay: 0.65s;
        }

        .x {
            position: absolute;
            right: 1rem;
            top: 1rem;
        }

        h3{
            width: 275px;
            font-family: 'Didot';
            font-style: normal;
            font-weight: 700;
            font-size: 66px;
            line-height: 85px;
            color: #611818;

            border-bottom: 2px solid;
            border-image-slice: 1;
            border-image-source: linear-gradient(90deg, #611818 0%, rgba(97, 24, 24, 0.0001) 100%);

        }

        button {
            width: 235px;
            height: 55px;
            left: 206px;
            top: 729px;

            background: linear-gradient(90deg, #611818 0%, #A36754 100%);
            border: 1px solid #979797;
            color: white;

            margin-top: 2rem;
        }
    }

    .hidden {
        pointer-events: none;
    }

    .main-text.fadeOut,
    .plus-button.fadeOut > span{
        clip-path: ellipse(0% 50% at 100% 50%);
    }
    

    .clicked {
        opacity: 100;
        animation: button-pressed 0.45s forwards;
    }

    .pop-out.closing {
        * {
            transform: translateX(0);
            opacity: 100;

            transition-delay: 0.65s;
        }
        transform: scale(1);
        opacity: 100;
        pointer-events: all;
        clip-path: ellipse(100% 100% at 50% 50%);
    }


    @keyframes button-pressed {
        
        50% {
            transform: scale(0.75);
        }
        90% {
            opacity: 100;
        }
        100% {
            opacity: 0;
        }
    }

    @keyframes text-glide {
        0% {
            transform: translateX(-100px);
            opacity: 0;
        }
        100% {
            transform: translateX(0);
            opacity: 100;
        }
    }

    @media (max-width:1000px) {
        .main-text {
            font-size: 75px;
            left: 20%;
        }

        .plus-button {
            font-size: 20px;
            top: 82%;
            left: 20%;
            
            img {
                width: 30px;
            }
        }

        .pop-out {
            width: 325px;


            height: 540px;

            padding-top: 0px;
            padding-left: 30px;
            padding-right: 30px;
            font-size: 0.75rem;

            transform-origin: 15% 100%;


            left: 7%;
            top: 5%;

            h3 {
                font-size: 35px;
                width: 200px;
                height: 75px;
            }

            button {
                width: 150px;
                height: 35px;
                margin-top: 0.25rem;
            }

        }
    }
</style>