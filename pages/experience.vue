<template lang="">
    
    <div class="experience ">
        <div class="scrollable-container">

            <div class="racesWrapper">
                <div>
                <h1 class="ml-32  text-black experience-title">Experience</h1>
                </div>
                <h2 class="year text-black">2020</h2>
                <div class="races">

                    <div class="year-card flex " 
                        v-for="experience in experience"
                        :key="experience.id"  
                        data-year="2017">

                        <div class="flex flex-row">

                            <div class=" flex image w-72 h-full "> </div>

                            <div class="detail flex flex-col">
                                <div>
                                    <h3 class="text-xl">{{experience.month}}</h3>
                                </div>
                                <div class="mt-16 space-y-8">
                                    <p class="job">{{experience.job}}</p>
                                    <p class="city">{{experience.city}}</p>
                                </div>
                                <p class="time">{{experience.time}}</p>

                            </div>
                        </div>
                    </div>

                    <!-- <div class="year-card" data-year="2017"></div>
                    <div class="year-card" data-year="2019"></div>
                    <div class="year-card" data-year="2021"></div>
                    <div class="year-card" data-year="2022"></div>
                    <div class="year-card" data-year="2023"></div> -->
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import Card from "../components/experience/card.vue"
import experience from '../../store/experiences.json';


export default {
    components: {
        Card,
    },
    data() {
        return {
            experience: experience
        };
    },
    methods: {
        ScrollAnimation(){
        gsap.registerPlugin(ScrollTrigger);

        const races = document.querySelector(".races");
        const h2 = document.querySelector(".year");
        const homeRef = this.$refs.homeRef;
        const titre = document.querySelector(".experience-title")
        

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
            start: "top 10%",
            end: () => `+=${getScrollAmount() * -1 }`,
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


    },
    
}

</script>
<style lang="css">
@import url('https://fonts.googleapis.com/css2?family=Inika:wght@400;700&family=Monoton&family=Orbitron:wght@500;600&display=swap');

.experience h2 {
    color: rgb(0, 0, 0);
    font-size: 180px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    font-family: 'monoton', sans-serif;
    letter-spacing: 25px;

}

.experience{
    margin-top: 50px;

}


.racesWrapper {
    position: flex;
    height: 100vh;
}

.year {
    color: white;
    font-size: 128px;
    display: flex;
    justify-content: center;
}

.races {
    width: fit-content;
    display: flex;
    flex-wrap: nowrap;
    margin: 0 auto;
    overflow: auto;
    /* Centrer horizontalement */
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

/* .year-card {
    background-color: red;
    width: 800px;
    height: 500px;
    border-radius: 25px;

    flex: 0 0 auto;
    margin-right: 15px;
} */


.year-card{
    background-color: white;
    width: 700px;
    height: 480px;
    border-radius: 25px;
    flex: 0 0 auto;
    margin-right: 15px;
    padding: 20px; 
    
}
.image{
    background-color: black;
    border-radius: 25px;
    height: 100%; 

}
.detail {
/* margin: 30px 25px;*/    
padding: 30px 25px;

}

.detail h3 {
    
    font-size: 80px;
    font-family: 'monoton', sans-serif; 
}

.detail p {
    color: #000;
    font-style: normal;
    line-height: normal
}
.job {
    font-weight: 300;
    font-size: 32px;

}

.city {
    font-weight: 200;
    font-size: 32px;

}

.time{
    margin-top: auto; 
    font-size: 24px;
    font-weight: 200;

}
</style>