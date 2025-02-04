<script setup>
//import { ref } from 'vue';

const skillsIcons = [
  {url: 'c-sharp-icon.png', alt: 'C#'},
  {url: 'net-maui-icon.png', alt: '.NET MAUI'},
  {url: 'html-icon.png', alt: 'HTML'},
  {url: 'css-3-icon.png', alt: 'CSS'},
  {url: 'js-icon.png', alt: 'JavaScript'},
  {url: 'vue-js-icon.png', alt: 'Vue.js'}
];

function getIconUrl(iconUrl) {
  return new URL(`../assets/images/skills/${iconUrl}`, import.meta.url).href;
}

</script>

<template>
<section id="skills">
  <div class="container">
    <div class="description">
      <h1>Habilidades</h1>
      <h2>Essas são as ferramentas que já usei em projetos ou cursos. </h2>
    </div>
    <div class="icons-wrapper">
      <img v-for="icon in skillsIcons" :src="getIconUrl(icon.url)" class="icon"/>
    </div>
  </div>
</section>

</template>

<style scoped>

.container{
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 60px;
  padding: 80px 100px 80px 100px;
}

.description h1,
.description h2{
  color: #272727;
}

.description h1{
  font-weight: 700;
  font-size: 36px;
}

.description h2{
  font-weight: 600;
  font-size: 20px;
}

.icons-wrapper{
  display: grid;
  grid-template-columns: repeat(5, 1fr); /* 5 ícones por linha */
  column-gap: 10vw;
  row-gap: 10vh;
}

.icon{
  width: 150px;
  height: 150px;
  margin: 0 auto;
  object-fit: contain;
}

@media (max-width: 1400px){
  .icons-wrapper{
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (max-width: 1280px){
  .icons-wrapper{
    grid-template-columns: repeat(3, 1fr);
  }
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

  .icons-wrapper{
    grid-template-columns: repeat(2, 1fr);
  }

  .icon {
    width: 100px;
    height: 100px;
  }
}


</style>