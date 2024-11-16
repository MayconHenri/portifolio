<script>
export default {
  name: "Navbar",
}
</script>

<template>
  <section id="sobre">
    <div class="intro">
      <h2>FULLSTACK DEVELOPER</h2>
      <h1>Hello, my name is Maycon Henrique</h1>
      <p>
        Sou um profissional fullstack, focado no desenvolvimento de soluções
        tanto para o front-end quanto para o back-end, com ênfase em tecnologias
        como Vue.js e JavaScript
      </p>
      <div class="buttons">
        <button class="projects">Projetos</button>
        <a href="https://linkedin.com/in/mayconnhenriique/" target="_blank"><button
            class="linkedin">LinkedIn</button></a>
      </div>
    </div>
    <div class="container">
      <img src="@/assets/yellow-bg.png" alt="Imagem" class="fixed-image" />
      <img src="@/assets/avatar/avatar1.png" alt="" class="avatar-image" />
    </div>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 1.5rem 2rem;
}

.fixed-image {
  position: absolute;
  top: 0;
  right: 0;
  max-width: 36rem;
  height: auto;
  z-index: -1;
  filter: grayscale(100%);
}

.intro {
  display: flex;
  flex-direction: column;
  margin-top: 4rem;
  margin-left: 7rem;
  text-align: left;
  width: 24rem;
  gap: 1rem;
}

.intro h2 {
  font-family: "Nunito", sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 1.2rem;
  color: #c6c6c6;
}

.intro h1 {
  font-family: "Playfair Display", serif;
  font-weight: 700;
  font-style: normal;
  font-size: 2.8rem;
}

.intro p {
  font-family: "Nunito", sans-serif;
  font-weight: 200;
  font-style: normal;
  font-size: 1.4rem;
  text-align: justify;
  color: #828282;
}

.avatar-image {
  max-width: 32rem;
  z-index: 2;
}

.buttons {
  display: flex;
  flex-direction: row;
  gap: 0.8rem;
}

.buttons button {
  padding: 0.4rem 1rem;
  font-family: "Roboto", sans-serif;
  font-weight: 400;
  font-style: normal;
  color: #25282b;
  font-size: 1rem;
  border: none;
  background-color: white;
  border-radius: 8px;
  cursor: pointer;
}

.buttons .projects {
  background-color: #828282;
  color: white;
}

.buttons .linkedin {
  border: 1px solid #25282b;
}

.buttons .linkedin,
.buttons .projects {
  transition: opacity 0.3s ease;
}

.buttons .linkedin:hover,
.buttons .projects:hover {
  opacity: 0.6;
}


@media (max-width: 600px) {
  .fixed-image {
    max-width: 20rem;
  }

  .avatar-image {
    max-width: 10rem
  }
}

@media (min-width: 600px) and (max-width: 1024px) {
  .fixed-image {
    max-width: 20rem;
  }

  .avatar-image {
    max-width: 20rem
  }

  .intro {
    margin-top: 2rem;
    margin-left: 4rem;
    text-align: left;
    width: 22rem;
  }

  .intro h2 {
    font-size: 1rem;
  }

  .intro h1 {
    font-size: 2.4rem;
  }

  .intro p {
    font-size: 1rem;
  }
  
}
</style>
