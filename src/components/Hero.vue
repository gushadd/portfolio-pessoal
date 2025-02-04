<script setup>
</script>

<template>
  <section id="hero">
    <div class="container">
      <div class="picture">
        <img src="../assets/images/profile.jpg" alt="Foto de Gustavo Haddad"/>
      </div>
      <div class="description">
        <div>
            <h1>Olá, meu nome é <span>Gustavo Haddad!</span></h1>
            <h2>Aqui você encontrará informações sobre 
              mim, meus projetos e habilidades!</h2>
        </div>
        <div class="social-media-icons">
          <a href="https://github.com/gushadd">
            <i class="fa-brands fa-github"></i>
          </a>
          <a href="https://www.linkedin.com/in/gustavo-haddad-985295250/">
            <i class="fa-brands fa-linkedin"></i>
          </a>
          <a href="mailto:gustavoeliashaddad@gmail.com">
            <i class="fa-regular fa-envelope"></i>
          </a>

        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

.container{
  margin-top: 80px; /* altura do cabeçalho */
  display: flex;
  height: 500px;
  padding: 80px 250px 80px 250px;
  gap: 80px;
}

.picture{
  display: flex;
  justify-content: center;
  flex:.3;
}

.picture img{
  border-radius: 50%;
  max-width: 400px;
  max-height: 400px;
  object-fit: cover;
}

.description{
  display: flex;
  flex-direction: column;
  flex: .7;
  justify-content: space-evenly;
}

.description h1{
  color: #272727;
  font-weight: 700;
  font-size: 32px;
}

.description h1 span{
  color: #D9405E;
  font-weight: 700;
}

.description h2{
  color:#272727;
  font-weight: 600;
  font-size: 24px;
}

.social-media-icons{
  display: flex;
  gap: 40px;
}

.social-media-icons i{
  color: #272727;
  font-size: 1.8rem;
  cursor: pointer;
  transition: opacity .13s;
}

.social-media-icons i:hover{
  opacity: .8;
}

@media (max-width: 1280px) {
  .container {
    flex-direction: column;
    text-align: center;
    height: auto;
    padding: 50px 5vw; /* vw = viewport witdh; 5vw = 5% da largura da tela */
    gap: 40px;
  }

  .picture img {
    max-width: 180px;
  }

  .description{
    gap: 50px;
  }

  .description h1 {
    font-size: 28px;
  }

  .description h2 {
    font-size: 20px;
  }

  .social-media-icons {
    justify-content: center;
    gap: 50px;
  }

  .social-media-icons i {
    font-size: 1.8rem;
  }
}

</style>