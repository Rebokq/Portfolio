<template lang="">
    <div class="home flex w-full flex-row h-full ml-16">

        <!-- Partie Gauche -->
        <div class="w-1/2 h-screen">
            <div class="flex items-center h-screen">
                <div class="flex flex-col">

                    <div class="mt-4 ml-4 mb-16 description">
                        <p class="text-3xl mb-4 font-light	">Hi, I'm <br /> </p>
                        <p class="text-4xl mb-6"><strong>Louis Kabore</strong><br /> </p>
                        <p class="text-3xl mb-4 font-normal pl-24">Front-end Developer <br /></p>
                        <p class="text-3xl font-light"> UX/UI Designer</p>
                    </div>

                    <div class="">
                        <NuxtLink to="/">
                            <nuxt-img
                                src="../public/assets/github.svg"
                                alt=""
                                class="float-left margin-fleche mr-4 w-14"
                                quality="30"
                            />
                        </NuxtLink>
                        <NuxtLink to="/">
                            <nuxt-img
                                :src="images.linkedin"
                                alt=""
                                class="float-left margin-fleche mr-4 w-14"
                                quality="30"
                                @mouseover="changeImage('linkedin')"
                                @mouseout="restoreImage('linkedin')"
                            />
                        </NuxtLink>
                        <NuxtLink to="/">
                            <nuxt-img
                                :src="images.figma"
                                alt=""
                                class="float-left margin-fleche mr-4 w-14"
                                quality="30"
                                @mouseover="changeImage('figma')"
                                @mouseout="restoreImage('figma')"
                            />
                        </NuxtLink>
                        <NuxtLink to="/">
                            <nuxt-img
                                :src="images.twitter"
                                alt=""
                                class="float-left margin-fleche mr-4 w-14"
                                quality="30"
                                @mouseover="changeImage('twitter')"
                                @mouseout="restoreImage('twitter')"
                            />
                        </NuxtLink>
                    </div>

                </div>
            </div>

        </div>

        <!-- Partie Droite -->
        <div class="w-1/2 relative">

          <div class="flex items-center h-screen relative">
            <div class="fixed z-1">
                <svg xmlns="http://www.w3.org/2000/svg" width="550" height="574" viewBox="0 0 473 474" fill="none">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M288.466 0C414.196 0 473 122.07 473 233.215C473 346.795 416.951 474 288.466 474C133.528 474 0 370.18 0 233.215C0 98.2632 135.805 0 288.466 0Z" fill="#FBEDDD"/>
                </svg>
            </div>
            <div class="z-10 relative flex  mb-96 ">
                <nuxt-img 
                    src="../public/assets/me.png"
                    class="myImage w-full"
                    quality="30"
                    

                />
            </div>
            <div class="flex">
                <div class="rectangle absolute z-20 bottom-40 left-10">
                    <div class="rectangle1 absolute z-20 left-0"></div>
                    <div class="rectangle2 absolute z-20 left-0 bottom-0"></div>
                </div>
            </div>

          </div>


        </div>

    </div>
</template>
<script>

export default {
    data() {
        return {

            images: {
                twitter: "../public/assets/twitter.svg",
                figma: "../public/assets/figma.svg",
                linkedin: "../public/assets/linkedin.svg",

            }
        }
    },
    methods: {
    changeImage(icon) {
        this.images[icon] = "../public/assets/" + icon + "-color.svg";
     

    },
    restoreImage(icon) {
        this.images[icon] = "../public/assets/" + icon + ".svg";

    }
  }

}

</script>
<style lang="css" scoped>
.p {
    line-height: 132px;
}
.myImage{
    width: 600px;
    max-width: 100%;

}
.rectangle1 {
    width: 494px;
    height: 154px;
    flex-shrink: 0;
    background: rgba(246, 220, 187, 0.60);
    filter: blur(10px);
}

.rectangle2 {
    width: 494px;
    height: 154px;
    flex-shrink: 0;
    background: #F6DCBB;
    filter: blur(10px);
    position: relative;
    bottom: -20px; /* Ajustez cette valeur en fonction de votre besoin */
}

.description{
    letter-spacing: 0.07em;
}
</style>