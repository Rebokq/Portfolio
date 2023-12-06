<template lang="">
    <div>
        <h1 class="ml-32 mt-8 text-black">Experience</h1>
        <div>

            <div class="racesWrapper">
                <h2 class="year text-black">2020</h2>
                <div class="races">
                    <div class="year-card" data-year="2017"></div>
                    <div class="year-card" data-year="2019"></div>
                    <div class="year-card" data-year="2021"></div>
                    <div class="year-card" data-year="2022"></div>
                    <div class="year-card" data-year="2023"></div>
                </div>
            </div>

        </div>
    </div>
</template>
<script>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';


export default {
    methods: {
        ScrollAnimation(){
            gsap.registerPlugin(ScrollTrigger);

        const races = document.querySelector(".races");
        const h2 = document.querySelector(".year");

        function getScrollAmount() {
            let racesWidth = races.scrollWidth;
            return -(racesWidth - window.innerWidth);
        }

        const tween = gsap.to(races, {
            x: getScrollAmount,
            duration: 3,
            ease: "none",
        });

        ScrollTrigger.create({
            trigger: ".racesWrapper",
            start: "top 0%",
            end: () => `+=${getScrollAmount() * -1}`,
            pin: true,
            animation: tween,
            scrub: 1,
            invalidateOnRefresh: true,
            markers: false,
            onUpdate: (self) => {
                // Fonction appelée à chaque mise à jour de ScrollTrigger
                const cards = document.querySelectorAll(".year-card");

                cards.forEach((card) => {
                    const cardRect = card.getBoundingClientRect();
                    const halfPage = window.innerWidth / 2;

                    if (cardRect.left <= halfPage && cardRect.right >= halfPage) {
                        // La carte est à la moitié de la page
                        const year = card.getAttribute("data-year");
                        h2.textContent = year;
                    }
                });
            },
        });
        }
    },
    mounted() {
        gsap.registerPlugin(ScrollTrigger);
        this.ScrollAnimation();

    }
}

definePageMeta({
  layout: "none"
}) 

</script>
<style lang="css">
h1 {
    color: rgb(0, 0, 0);
    font-size: 64px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
}

body {
    margin: 0;
    height: 100%;
    overflow-x: hidden;
}

.racesWrapper {
    position: relative;
    height: 100vh;
}

.year {
    color: white;
    font-size: 200px;
    display: flex;
    justify-content: center;
}

.races {
    width: fit-content;
    display: flex;
    flex-wrap: nowrap;
    margin: 0 auto;
    /* Centrer horizontalement */
}
.year-card {
    color: black;
}

.year-card:first-child {
    margin-left: 50vw;
    /* La moitié de la largeur de la fenêtre */
}

.year-card:last-child {
    margin-right: 30vw;
    /* La moitié de la largeur de la fenêtre */
}




.space-20vh {
    height: 20vh;
}

.space-30vh {
    height: 30vh;
}

.space-50vh {
    height: 50vh;
}

.space-100vh {
    height: 100vh;
}

.year-card {
    background-color: red;
    width: 800px;
    height: 500px;
    border-radius: 25px;

    flex: 0 0 auto;
    margin-right: 15px;
    /* Marge entre les cartes */
}
</style>