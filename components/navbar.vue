<template lang="">
    <div class="w-screen p-4" >

        <div class="navbar-wrapper flex justify-between place-items-center items-center py-2">

            <div class="flex justify-between place-items-center items-center py-2">
                <div>
                    <div class="">
                        <ul class="flex flex-row space-x-64 pl-32 text-xl font-light"> 
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

    </div>
</template>
<script>
export default {

}
</script>
<script setup>
const route = useRoute()

</script>
<style lang="css">
.boutton-contact {
    border-color: rgb(251, 237, 221);
    transition: border-radius 1s ease-out, background-color 1s ease-out;


}

.boutton-contact:hover {
    background-color: rgb(251, 237, 221);
    border-radius: 50%;
    transition: border-radius 0.5s ease-out, background-color 0.5s ease-out;

}
a{
    color: #000000;

}
li{
    color: #000000;
}

li:after {
  display:block;
  content: '';
  border-bottom: solid 2px #000;  
  transform: scaleX(0);  
  transition: transform 350ms ease-in-out;
  transform-origin: 100% 50%; 
  padding-top: 4px;
}

li:hover:after { transform: scaleX(1); }
li:after{  transform-origin:  0% 50%; }

li:not(:hover):after { transform-origin:  100% 50%; }

.navbar-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
}
</style>