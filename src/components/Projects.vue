<script setup>
import { ref, computed, onMounted } from 'vue';
import { Carousel, Slide, Pagination } from 'vue3-carousel';
import "vue3-carousel/dist/carousel.css"
import ProjectCard from './ProjectCard.vue';

const windowWidth = ref(window.innerWidth);

const projectsCarouselItemsToShow = computed(() => {
  if (windowWidth.value < 800) return 1;
  if (windowWidth.value < 1280) return 1.5;
  return 2.5;
});

onMounted(() => {
  window.addEventListener('resize', () => {
    windowWidth.value = window.innerWidth;
  });
});

const carouselConfig = computed(() => ({
  itemsToShow: projectsCarouselItemsToShow.value,
  wrapAround: true
}));


const projects = ref([
  {
    title: 'TolyID',
    description: 'Desenvolvido em grupo com o objetivo de ajudar na preservação de uma espécie de tatu bola.',
    link: 'https://github.com/gushadd/pei-III-toly-id-mobile',
    tools: ['NET MAUI', 'SQLite'],
    isFinished: false
  },
  {
    title: 'Contador de Dinheiro',
    description: 'Aplicativo de contagem de notas e moedas de Real (R$) feito utilizando o .NET MAUI.',
    link: 'https://github.com/gushadd/netmauiapp-contador-de-dinheiro',
    tools: ['NET MAUI', 'SQLite'],
    isFinished: true
  },
  {
    title: 'Conversor de Moedas',
    description: 'Simples aplicativo de conversão de moedas, desenvolvido com .NET MAUI.',
    link: 'https://github.com/gushadd/netmauiapp-conversor-de-moedas',
    tools: ['NET MAUI', 'SQLite'],
    isFinished: true
  },
]);

</script>

<template>
  <section id="projects">
    <div class="container">
      <div class="description">
        <h1>Projetos</h1>
        <h2>Aqui estão alguns os meus projetos, criados com muita dedicação!</h2>
      </div>
      <Carousel class="projects" v-bind="carouselConfig">
        <Slide v-for="(project, index) in projects" :key="index">
          <ProjectCard :title="project.title" :description="project.description" :link="project.link" :tools="project.tools" :is-finished="project.isFinished"/>
        </Slide>
  
        <template #addons>
          <Pagination />
        </template>
      </Carousel>
    </div>
  </section>
</template>

<style scoped>
.container{
  display: flex;
  flex-direction: column;
  background-color: #232E42;
  height: auto;
  gap: 60px;
  padding: 80px 100px 80px 100px;
}

.description{
  flex: .2;
}

.description h1,
.description h2{
  color: #ffffff;
}

.description h1{
  font-weight: 700;
  font-size: 36px;
}

.description h2{
  font-weight: 600;
  font-size: 20px;
}

.projects{
  flex: .8;
  display: flex;
  gap: 50px;
}

@media (max-width: 768px) {
  .container{
    padding: 50px 5vw; /* vw = viewport witdh; 5vw = 5% da largura da tela */
  }

  .description h1{
    font-size: 26px;
  }

  .description h2{
    font-size: 18px;
  }
}
</style>