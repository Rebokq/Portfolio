<template>
    <div class="flex h-screen">

        <div>
<!--             <div class="dot z-1"> </div>
 -->            <div class="z-10">
                <slot />
            </div>
        </div>

    </div>
</template>

<script>
export default {
    mounted() {
        const dot = document.querySelector(".dot");
        let mouseX = 0;
        let mouseY = 0;
        let dotX = 0;
        let dotY = 0;
        const inertia = 0.1; // Réglage du retard, plus la valeur est basse, plus le retard est grand

        window.addEventListener("mousemove", (e) => {
            dot.style.visibility = "visible";
            mouseX = e.clientX;
            mouseY = e.clientY;
        });

        function animateDot() {
            const dx = mouseX - dotX;
            const dy = mouseY - dotY;

            dotX += dx * inertia;
            dotY += dy * inertia;

            dot.style.top = `${dotY}px`;
            dot.style.left = `${dotX}px`;

            requestAnimationFrame(animateDot);
        }

        animateDot();


    }

}
</script>

<style lang="css" scoped>
* {
    background-color: #F6DCBB;
    margin: 0;
    padding: 0;
/*     cursor: none;
 */}

.dot {
    visibility: hidden;
    position: absolute;
    /*   width:18%;
  height: 18%; */
    width: 35px;
    height: 35px;
    border-radius: 100%;
    background-color: whitesmoke;
    box-shadow: 0 0 90px 90px rgba(255, 255, 255, 0.6);
    /* Effet de flou circulaire */
    overflow: hidden;
    filter: blur(20px);
    /* Ajoutez cette ligne pour appliquer un flou de 10 pixels */

}
</style>