<script>
export default {
  name: "Navbar",
}
</script>

<template>
  <section>
    <div class="intro">
      <h2>FULLSTACK DEVELOPER</h2>
      <h1>Hello, my name is Maycon Henrique</h1>
      <p>
        Sou um profissional fullstack, focado no desenvolvimento de soluções
        tanto para o front-end quanto para o back-end, com ênfase em tecnologias
        como Vue.js e JavaScript
      </p>
      <div class="buttons">
        <button class="projects">Projects</button>
        <button class="linkedin">LinkedIn</button>
      </div>
    </div>
    <div class="container">
      <img src="@/assets/yellow-bg.png" alt="Imagem" class="fixed-image" />
      <img src="@/assets/avatar1.png" alt="" class="avatar-image" />
    </div>
  </section>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&family=Nunito:ital,wght@0,200..1000;1,200..1000&family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&family=Nunito:ital,wght@0,200..1000;1,200..1000&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap");
section {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.fixed-image {
  position: absolute;
  top: 0;
  right: 0;
  width: 36rem;
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
  width: 32rem;
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
  color: #25282B;
  font-size: 1rem;
  border: none;
  background-color: white;
  border-radius: 8px;
  cursor: pointer;
}

.buttons .projects {
  background-color: #828282;
}
.buttons .linkedin {
  border: 1px solid #25282B;
}

.buttons .linkedin, .buttons .projects {
  transition: opacity 0.3s ease;
}

.buttons .linkedin:hover, .buttons .projects:hover {
  opacity: 0.6; 
}
</style>
