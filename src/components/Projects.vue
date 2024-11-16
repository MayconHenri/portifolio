<script>
export default {
  name: "Projects",
  data() {
    return {
      CardRows: [
        {
          title: "Teste",
          descrption: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet voluptates porro adipisci eum accusamus, quibusdam, sit odit mollitia vitae soluta necessitatibus veritatis dolore. Perspiciatis nisi soluta accusamus velit, eveniet autem?",
          LinkImg: 'https://plus.unsplash.com/premium_photo-1731021470631-255095ce4045?q=80&w=1987&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
        },
        {
          title: "Teste",
          descrption: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet voluptates porro adipisci eum accusamus, quibusdam, sit odit mollitia vitae soluta necessitatibus veritatis dolore. Perspiciatis nisi soluta accusamus velit, eveniet autem?",
          LinkImg: 'https://plus.unsplash.com/premium_photo-1731021470631-255095ce4045?q=80&w=1987&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
        },
        {
          title: "Teste",
          descrption: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet voluptates porro adipisci eum accusamus, quibusdam, sit odit mollitia vitae soluta necessitatibus veritatis dolore. Perspiciatis nisi soluta accusamus velit, eveniet autem?",
          LinkImg: 'https://plus.unsplash.com/premium_photo-1731021470631-255095ce4045?q=80&w=1987&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
        }
      ]
    }
  }
}
</script>

<template>
  <section id="projetos">
    <div class="title">
      <h1>Projetos</h1>
      <img src="@/assets/Rectangle19.png" alt="Tarja sobre o nome">
    </div>
    <div class="cards">
      <div class="card" v-for="(card, index) in CardRows" :key="index" :class="{ 'reverse-card': index % 2 !== 0 }">
        <div class="description">
          <h1>{{ card.title }}</h1>
          <p>{{ card.descrption }}</p>
          <button>View Project</button>
        </div>
        <div class="image">
          <img :src="card.LinkImg" alt="Imagem do Projeto">
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
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
}

.reverse-card .image img {
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 8px;
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
  color: #25282B;
}

.description p {
  text-align: justify;
  font-family: "Nunito", sans-serif;
  font-weight: 300;
}

.description button {
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
</style>
