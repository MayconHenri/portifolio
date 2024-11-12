<script>
export default {
  name: "Navbar",
}
</script>

<template>
  <nav>
    <div class="title-name">Maycon Henrique</div>
    <div class="links">
      <ul>
        <li><a href="">About</a></li>
        <li><a href="">Projects</a></li>
        <li><a href="">Contacts</a></li>
      </ul>
    </div>
  </nav>
  
</template>


<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&display=swap");

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


</style>
