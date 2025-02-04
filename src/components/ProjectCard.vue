<script setup>
const props = defineProps({
  title: String,
  description: String,
  link: String,
  tools: Array,
  isFinished: Boolean
});
</script>

<template>
  <div class="card">

    <div class="top">
      <h2>{{ title }}</h2>
      <h3 v-if="isFinished" class="finished">Completo</h3>
      <h3 v-else class="not-finished">Em desenvolvimento</h3>
    </div>

    <div class="tools">
      <h3 v-for="(tool, index) in tools" :key="index">{{ tool }}</h3>
    </div>

    <div class="description">
      <h3>{{ description  }}</h3>
    </div>

    <div class="project-link">
      <a :href="link">Ver</a>
    </div>

  </div>
</template>

<style scoped>
.card{
  display: flex;
  flex-direction: column;
  height: 550px;
  width: 500px;
  background-color: white;
  border-radius: 20px;
  padding: 20px;
  gap: 10px;
}

.top{
  display: flex;
  justify-content: space-between;
  align-items: start;
}


.top h2{
  color: #272727;
  font-weight: 700;
  font-size: 24px;
  max-width: 50%;
}

.finished,
.not-finished{
  font-weight: 600;
  font-size: 15px;
  padding: 2px 13px;
  margin-top: 5px;
  border-radius: 20px;
}

.finished{
  color: #006723;
  background-color: #CEEED9;
}

.not-finished{
  color: #7E7400;
  background-color: #FEF69E;
}

.tools{
  display: flex;
  gap: 10px;
}

.tools h3{
  color: #232E42;
  font-weight: 600;
  font-size: 15px;
  background-color: #D2DBEA;
  padding: 2px 13px;
  border-radius: 20px;
}

.description{
  margin-top: 15px;
  max-height: 50%;
  overflow: hidden;
}

.description h3{
  color: #272727;
  font-size: 18px;
  max-height: 100%;
}

.project-link{
  margin-top: 15px;
  display: flex;
  justify-content: center;
}

.project-link a{
  text-decoration: none;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  width: 140px;
  border: none;
  background-color: #D9405E;
  border-radius: 10px;
  color: #ffffff;
  font-weight: 600;
  font-size: 16px;
  cursor: pointer;
  transition: background-color .2s;
}

.project-link a:hover{
  background-color: #DA5670;
}

@media (max-width: 768px) {
  .card {
    padding: 15px;
    max-width: 90%;
  }

  .description h2 {
    font-size: 18px;
  }


  .bottom a {
    width: 120px;
    height: 45px;
    font-size: 14px;
  }
}
</style>