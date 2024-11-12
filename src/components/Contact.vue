<script>
export default {
  name: "Contact",
  
}
</script>

<template>
  <section>
    <div class="title">
      <h1>Contacts</h1>
      <img src="@/assets/Rectangle19.png" alt="Tarja sobre o nome">
    </div>
    <div>
      <form action="">
        <label for="Name">Name</label>
        <input type="text" name="Name" id="Name">
        <label for="E-mail">E-mail</label>
        <input type="text" name="Email" id="Email">
        <label for="Mensagem">Mensagem</label>
        <input type="text" name="Mensagem" id="Mensagem">
      </form>
    </div>
  </section>
</template>


<style scoped>
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
  filter: grayscale(100%);
}
form {
  display: flex;
  flex-direction: column;
  margin-top: 2rem
}
</style>
