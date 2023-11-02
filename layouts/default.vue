<template>
    <div class="flex flex-col h-screen w-screen">
        <div class="">
            <header>
                <Navbar/>
            </header>
        </div>
        <div>
            <div class="z-10">
                <slot />
            </div>
        </div>

    </div>
</template>

<script>
/* export default {
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

} */
</script>

<style lang="css" scoped>
* {
    background-color: #F6DCBB;
    margin: 0;
    padding: 0;
    /*     cursor: none;
 */
}</style> 