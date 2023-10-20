<template lang="">
    <div class="w-screen p-4">
        <div class="flex justify-between place-items-center">
            <div>
                <div class="">
                <ul class="flex flex-row space-x-32 pl-16 text-xl"> 
                    <li>Projects</li>
                    <li>Experiences</li>
                </ul>
            </div>
            
            </div>
            <div>
                <a class="text-5xl">LK</a>
            </div>
          
            <div> <div class="">
                <ul class="flex flex-row space-x-32 pr-16 text-xl place-items-center"> 
                    <li>About me</li>
                    <li>
                        <button class="boutton-contact p-2 px-8 rounded-super border-2 border-red-500 ">Contact me</button>
                    </li>
                </ul>
            </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="css">
    .boutton-contact{
        border-color: rgb(251, 237, 221);

        
    }
    .boutton-contact:hover{
        background-color: rgb(251, 237, 221);
        border-radius: 50%;
        transition: border-radius 0.5s ease, background-color 0.5s ease;

    }
</style>