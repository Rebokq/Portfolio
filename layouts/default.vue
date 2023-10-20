<template>
    <div class="flex h-screen">

        <div>
            <div class=dot></div>
            <slot />
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
}
.dot {
  visibility: hidden;
  position: absolute;
  width: 0.1px;
  height: 0.1px;
  border-radius: 100%;
  background-color: whitesmoke;
  box-shadow: 0 0 80px 80px rgba(255, 255, 255, 0.6); /* Effet de flou circulaire */
  overflow: hidden;
}
</style>