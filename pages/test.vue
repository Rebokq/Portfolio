<template lang="">
    <div>
        <div class="year-card flex " data-year="2017">
            <div class="flex flex-row">

                <div class=" flex image w-72 h-full ">
                <nuxt-img 
                    src="../public/assets/Post_University.svg.png"
                    alt=""
                    class="float-left margin-fleche p-4 w-14 object-contain w-full"
                    quality="30"
                />
                </div>

                <div class="detail flex flex-col">
                    <div>
                        <h3 class="text-xl">AUG</h3>
                    </div>
                    <div class="mt-16 space-y-8">
                        <p class="job">Post University</p>
                        <p class="city">Waterbury - CT</p>
                    </div>
                    <p class="time">2017 - 2021</p>

                </div>
            </div>
        </div>
        
    </div>
</template>
<script>
export default {

    data(){
        return {
            images: {
                job: "../public/assets/Post_University.svg.png",
            }
        }
    }
}
definePageMeta({
  layout: "none"
}) 
</script>
<style lang="css">
@import url('https://fonts.googleapis.com/css2?family=Inika:wght@400;700&family=Monoton&family=Orbitron:wght@500;600&display=swap');

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