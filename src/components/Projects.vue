<script>
import CookinImg from "@/assets/projects/cookin.png"
import BlogImg from "@/assets/projects/blog.png"
import NotasImg from "@/assets/projects/notas.png"

export default {
  name: "Projects",
  data() {
    return {
      CardRows: [
        {
          title: "Cookin' Up",
          descrption:
            "Aplicação para entusiastas culinários explorarem novas receitas, utilizando ingredientes disponíveis. Desenvolvido com Vue.js e TypeScript.",
          LinkImg: CookinImg,
          link: "https://github.com/MayconHenri/CookinUp"
        },
        {
          title: "Blog de Culinária",
          descrption:
            "Blog de culinária desenvolvido com PHP, JavaScript, Bootstrap e um banco de dados para armazenar receitas e dicas gastronômicas.",
          LinkImg: BlogImg,
          link: "https://github.com/MayconHenri/BlogCulinaria"
        },
        {
          title: "GuardaNotas",
          descrption:
            "Aplicação para salvar notas online. Adicione, edite e exclua suas ideias facilmente com uma interface amigável.",
          LinkImg: NotasImg,
          link: "https://github.com/MayconHenri/projeto-todolist"
        },
      ],
    }
  },
  methods: {
    goToRepo(link) {
      window.open(link, "_blank");
    }
  }
}
</script>


<template>
  <section id="projetos">
    <div class="title">
      <h1>Projetos</h1>
      <img src="@/assets/Rectangle19.png" alt="Tarja sobre o nome" />
    </div>
    <div class="cards">
      <div
        class="card"
        v-for="(card, index) in CardRows"
        :key="index"
        :class="{ 'reverse-card': index % 2 !== 0 }"
      >
        <div class="description">
          <h1>{{ card.title }}</h1>
          <p>{{ card.descrption }}</p>
          <button @click="goToRepo(card.link)">View Project</button>
        </div>
        <div class="image">
          <img :src="card.LinkImg" alt="Imagem do Projeto" />
        </div>
      </div>
    </div>
  </section>
</template>


<style scoped>
section {
  background-color: #c6c6c6;
  padding: 0.4rem 0 6rem;
}

.title {
  margin-top: 2rem;
  text-align: center;
  position: relative;
}

.title h1 {
  font-family: "Playfair Display", serif;
  font-weight: 700;
  font-size: 2.8rem;
}

.title img {
  filter: brightness(0) invert(1);
}

.cards {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: center;
}

.card {
  display: flex;
  flex-direction: row;
  width: 50rem;
  height: 24rem;
  border-radius: 8px;
  background-color: white;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
  transition: transform 0.5s cubic-bezier(0.25, 0.1, 0.25, 1);
}

.reverse-card {
  flex-direction: row-reverse;
}

.card:hover {
  transform: translate(8px, 8px);
}

.image img {
  width: 20rem;
  height: 24rem;
  object-fit: cover;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
  display: block;
}

.reverse-card .image img {
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 8px;
  display: block;
}

.description {
  padding: 2rem 4rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1.2rem;
}

.description h1 {
  text-align: left;
  font-family: "Playfair Display", serif;
  font-weight: 700;
  font-size: 1.6rem;
  color: #25282b;
}

.description p {
  text-align: justify;
  font-family: "Nunito", sans-serif;
  font-weight: 300;
}

.description button {
  color: #000;
  width: 8rem;
  padding: 0.4rem 1rem;
  border: 1px solid black;
  background-color: white;
  border-radius: 12px;
  cursor: pointer;
  transition: opacity 0.3s ease;
  font-family: "Roboto", sans-serif;
}

.description button:hover {
  opacity: 0.6;
}

@media (max-width: 1024px) {
  .card {
    width: 40rem;
    height: auto;
    flex-direction: column;
  }

  .image img {
    width: 100%;
    height: 16rem;
    border-radius: 0 0 8px 8px;
    display: block;
  }

  .reverse-card {
    flex-direction: column;
  }

  .reverse-card .image img {
    border-radius: 0 0 8px 8px;
  }

  .description {
    padding: 1.5rem 2rem;
  }
}

@media (max-width: 768px) {
  .card {
    width: 90%;
    flex-direction: column;
  }

  .image img {
    height: 12rem;
  }

  .reverse-card .image img {
    border-radius: 0 0 8px 8px;
  }

  .description h1 {
    font-size: 1.4rem;
  }

  .description p {
    font-size: 1rem;
  }

  .description button {
    width: 100%;
    text-align: center;
  }
}

@media (max-width: 480px) {
  .card {
    width: 80%;
  }

  .image img {
    height: 10rem;
    border-radius: 0 0 8px 8px;
    display: block;
  }

  .reverse-card .image img {
    border-radius: 0 0 8px 8px;
  }

  .description {
    padding: 1rem;
  }

  .description h1 {
    font-size: 1.2rem;
  }

  .description p {
    font-size: 0.9rem;
  }
}
</style>
