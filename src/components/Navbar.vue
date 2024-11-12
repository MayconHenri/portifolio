<script>
export default {
  name: "Navbar",
}
</script>

<template>
  <nav>
    <div class="title-name">
      <h1>Maycon Henrique</h1>
    </div>
    <div class="links">
      <ul>
        <li><a href="#sobre">Sobre Mim</a></li>
        <li><a href="#projetos">Projetos</a></li>
        <li><a href="#contatos">Contatos</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>

* {
  margin: 0;
  padding: 0;
  box-shadow: 0;
  font-family: "Comfortaa", sans-serif;
  list-style-type: none;
  text-decoration: none;
  font-size: 1.2rem;
  color: #25282B;
}

nav {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 1rem;
  position: relative;
}

.title-name {
  font-weight: 700;
  margin-left: 7rem;
}

.links {
  margin-right: 7rem;
}

.links ul {
  font-weight: 500;
  display: flex;
  flex-direction: row;
  gap: 1rem;
}

.links a, .title-name h1 {
  transition: opacity 0.3s ease;
  cursor: pointer;
}

.links a:hover, .title-name h1:hover {
  opacity: 0.6; 
}

</style>
