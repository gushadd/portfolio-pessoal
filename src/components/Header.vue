<script setup>

const scrollToSection = (id) => {
  const section = document.getElementById(id);
  if (section){
    section.scrollIntoView({ behavior: "smooth" })
  }
};

</script>

<template>
  <nav class="container">
    <div class="route" @click="scrollToSection('hero')">
      <h1>Perfil</h1>
    </div>
    <div class="route" @click="scrollToSection('projects')">
      <h1>Projetos</h1>
    </div>
    <div class="route" @click="scrollToSection('skills')">
      <h1>Habilidades</h1>
    </div>
  </nav>
</template>

<style scoped>
.container{
  position: fixed;
  width: 100%;
  top: 0;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 100px;
  height: 80px;
  background-color: #232E42;
  z-index: 1000;
}

.container h1{
  color: white;
  font-weight: 400;
  font-size: 20px;
}

.route{
  background-color: #232E42;
  padding: 10px 20px 10px 20px;
  border-radius: 10px;
  cursor: pointer;
  transition: background-color .13s;
}

.route:hover{
  background-color: #364768;
}

@media (max-width: 768px){
  .container {
    
    gap: 10px;
    height: auto;
    padding: 20px 0;
  }

  .route {
    width: 100%; /* Faz os itens ocuparem a largura toda */
    text-align: center;
  }

  .container h1 {
    font-size: 18px; /* Reduz o tamanho da fonte */
  }
}

</style>