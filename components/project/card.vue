<template lang="">
    <div>
        <div class="flex justify-around mr-8 ml-8">  

            <div class="project-container" @click="openNav">
                <div class="card">
                    <h1 class="text-white"></h1>
                </div>
                <h2 class="mb-4">Project Name</h2>
                <div class="flex items-center hover:mb-4">
                    <NuxtLink class="flex items-center" to="/">
                        <nuxt-img
                            src="../public/assets/arrow.png"
                            alt=""
                            class=" mr-2 w-8"
                            quality="30"
                        />
                        <a class="">Read More</a>
                    </NuxtLink>
                </div>
            </div>

            <div class="project-container">
                <div class="card">
                    <h1 class="text-white"></h1>
                </div>
                <h2 class="mb-4">Project Name</h2>
                <div class="flex items-center">
                    <NuxtLink class="flex items-center" to="/">
                        <nuxt-img
                            src="../public/assets/arrow.png"
                            alt=""
                            class=" mr-2 w-8"
                            quality="30"
                        />
                        <a class="">Read More</a>
                    </NuxtLink>
                </div>
            </div>

            <div class="project-container">
                <div class="card">
                    <h1 class="text-white"></h1>
                </div>
                <h2 class="mb-4">Project Name</h2>
                <div class="flex items-center">
                    <NuxtLink class="flex items-center" to="/">
                        <nuxt-img
                            src="../public/assets/arrow.png"
                            alt=""
                            class=" mr-2 w-8"
                            quality="30"
                        />
                        <a class="">Read More</a>
                    </NuxtLink>
                </div>
            </div>

            <div class="project-container">
                <div class="card">
                    <h1 class="text-white"></h1>
                </div>
                <h2 class="mb-4">Project Name</h2>
                <div class="flex items-center">
                    <NuxtLink class="flex items-center" to="/">
                        <nuxt-img
                            src="../public/assets/arrow.png"
                            alt=""
                            class=" mr-2 w-8"
                            quality="30"
                        />
                        <a class="">Read More</a>
                    </NuxtLink>
                </div>
            </div>
        </div>

        
    </div>
    
</template>
<script>
export default {
    methods: {
    openNav() {
      event.stopPropagation();


      document.getElementById("mySidenav").style.height = "75%";
    },


  },

}



</script>
<style lang="css">

    .card{
        width: 400px;
        height: 500px;
        border-radius: 15px;
        background: #FBEDDD;
        margin-bottom: 32px;
    }
    h2{
        color: #F6DCBB;
        font-family: Inter;
        font-size: 32px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;    
        }
    a{
        color: #2176E2
    }

    .project-container{
        transition: all 0.7s ease-out;
        cursor: pointer;

    }
    .project-container:hover {
        transform: translate3d(0px, -2rem, 0px) scale3d(1, 1, 1) rotateX(0deg) rotateY(0deg) rotateZ(0deg) skew(0deg, 0deg);

    }

</style>