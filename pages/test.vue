<template lang="">
    <div>
        <div class="year-card" data-year="2017">
            <div class="flex">
                <div class="image object-cover w-72 h-full  "></div>

                <div class="detail flex ">
                    <p class="text-center text-xl">JUL</p>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
definePageMeta({
  layout: "none"
}) 

</script>

<style lang="css">
.year-card {
    background-color: white;
    width: 700px;
    height: 480px;
    border-radius: 25px;
    flex: 0 0 auto;
    margin-right: 15px;
    padding: 20px;
    display: flex;
}

.image {
    background-color: black;
    border-radius: 25px;
}

.detail {
    background-color: grey;
    border-radius: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.detail h3 {
    display: center;
    font-size: 200px;
}
</style>
