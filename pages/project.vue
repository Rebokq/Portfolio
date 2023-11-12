<template lang="">
    <div class="main" >
        <h1 class="title ml-32 mt-8">Projects</h1>
        <div class="mt-16">
          
            <div>
                <div id="mySidenav" class="sidenav" >
                  <div class="side-content">
                    <div  class="mb-8">
                      
                        <nuxt-img
                          src="../public/assets/close-button.svg"
                          alt=""
                          class="flex float-right w-16 pointer"
                          @click="closeNav"
                        />
                      
                      <h2>{{ selectedProject.name }}</h2>
                    </div>

                    <div class="flex">

                      <div class="project-detail flex w-1/2 items-center">
                        <div class="float project-img"> </div>
                        <p class="text-center px-16 tracking-widest">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</p>
                        <div class="line w-1 bg-gray-500"></div>
                      </div>
                      
                      <div class="flex flex-col  w-1/2">
                        <h3 class="text-4xl text-center mb-4">Techno</h3>

                        <div class="flex justify-center grid grid-cols-4 gap-8 px-56">
                          <div class="cercle"></div>
                          <div class="cercle"></div>
                          <div class="cercle"></div>
                          <div class="cercle"></div>
                          <div class="cercle"></div>
                          <div class="cercle"></div>

                        </div>
                      </div>

                    </div>
                   
                </div>
              </div>
            </div>

            <Card @projectSelected="showProjectDetails" />


        </div>
    </div>
</template>
<script setup>
definePageMeta({
  layout: "dark-nav"
}) 
</script>

<script>
import Card from "../components/project/card.vue"
import BottomNav from "../components/project/bottom.vue"
import projects from '../store/projects.json';

export default {
  components: {
    Card,
    BottomNav,
  },
  data() {
    return {
      selectedProject: {} // Détails du projet sélectionné
    };
  },

  methods: {
   
    closeNav(){
      document.getElementById("mySidenav").style.height = "0";

    },
    closeNavOnBodyClick() {
      if (!document.getElementById("mySidenav").contains(event.target)) {
      document.getElementById("mySidenav").style.height = "0";
      }      
    },
    showProjectDetails(project) {
      this.selectedProject = project;
      document.getElementById("mySidenav").style.height = "75%";
    },

  },

  mounted() {
    // Ajoute un écouteur d'événements au chargement du composant
    document.body.addEventListener("click", this.closeNavOnBodyClick);
  },
  beforeUnmount() {
    // Assurez-vous de retirer l'écouteur d'événements lorsque le composant est déchargé
    document.body.removeEventListener("click", this.closeNavOnBodyClick);
  }
};
</script>
<style lang="css">
.cercle{
  background-color: #FBEDDD;
  padding: 50px;
  width: 50px;
  border-radius: 50%;
}
.line{
  height: 500px;
}

.project-detail p {
  color: #000;
text-align: center;
font-family: Inter;
font-size: 32px;
font-style: normal;
font-weight: 200;
line-height: normal;
}
.project-img{
width: 400px;
height: 500px;
background-color: #FBEDDD;
border-radius: 25px;
padding: 150px;
margin: 0;
}
.side-content{
  padding: 32px;

}
.side-content h2{
  color: black;
  font-size: 64px;


}
.sidenav {
  height: 0%;
  width: 100%;
  position: fixed;
  bottom: 0;
  left: 0;
  background-color: #F6DCBB;
  transition: height 1s;
  overflow-x: hidden;
  z-index: 1;
  border-radius: 35px;
}

.title {
  color: #F6DCBB;
  font-size: 64px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}

.bottomNav-enter {
  transform: translateY(-100%);
}

.bottomNav-enter-active {
  transform: translateY(0);
  transition: transform 1s ease-in;
}

.bottomNav-leave {
  transform: translateY(0);
}

.bottomNav-leave-active {
  transform: translateY(100%);
  transition: transform 1s ease-out;
}
</style>
