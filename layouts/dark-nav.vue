<template>
    <div class="home">
    <div class="h-screen w-screen">
        <div class="flex">
            <header>
                <!-- <DarkNav/> -->
                <div class="w-screen p-2">
                    <div class="flex justify-between place-items-center items-center py-2 text-white">
                        <div>
                            <div class="">
                                <ul class="flex flex-row space-x-32 pl-32 text-xl font-light"> 
                                    <li><NuxtLink to="/project">Projects</NuxtLink></li>
                                    <li><NuxtLink to="/experience">Experiences</NuxtLink></li>
                                </ul>
                            </div>

                        
                        </div>
                        <div>
                            <NuxtLink to="/"><a class="text-5xl">LK</a></NuxtLink>
                        </div>
                    
                        <div> 
                            <div class="">
                                <ul class="flex flex-row space-x-64 pr-32 text-xl place-items-center font-light"> 
                                    <li><NuxtLink to="/about">About me</NuxtLink></li>
                                    
                                    <NuxtLink class="" to="/contact">
                                        <button class="boutton-contact p-2 px-8 rounded-super border-2 border-red-500 ">Contact me</button>
                                    </NuxtLink>
                                    
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>

            </header>
        </div>
        <div>
            <div class="h-screen MT-8">
                <slot />
            </div>
        </div>

    </div>
</div>
</template>

<script>
</script>

<style lang="css" scoped>
* {
    background-color: #000000;
    margin: 0;
    /*     cursor: none;
 */
}
.home{
    margin: 0;
    height: 100%;
    overflow: hidden;
}
.boutton-contact {
    border-color: rgb(251, 237, 221);
    transition: border-radius 1s ease-out, background-color 1s ease-out;
color: #F6DCBB;

}

.boutton-contact:hover {
    background-color: rgb(251, 237, 221);
    border-radius: 50%;
    transition: border-radius 0.5s ease-out, background-color 0.5s ease-out, color 0.5s ease-out;
    color: #000000;

}
a{
    color: #F6DCBB;

}
li{
    color: #F6DCBB;
}

li:after {
  display:block;
  content: '';
  border-bottom: solid 2px #F6DCBB;  
  transform: scaleX(0);  
  transition: transform 350ms ease-in-out;
  transform-origin: 100% 50%; 
  padding-top: 4px;
}

li:hover:after { transform: scaleX(1); }
li:after{  transform-origin:  0% 50%; }

li:not(:hover):after { transform-origin:  100% 50%; }
</style> 