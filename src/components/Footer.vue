<script>
export default {
  name: "Footer",
}
</script>

<template>
  <footer>
    <div class="icons">
      <a href="https://github.com/MayconHenri" target="_blank">
        <img src="../assets/icons/github-mark.png" alt="Icone GitHub"></a>
      <a href="https://linkedin.com/in/mayconnhenriique/" target="_blank">
        <img src="../assets/icons/linkedin.png" alt="Icone Linkedin"></a>
      <a href="mailto:maycon.moreiira@hotmail.com" target="_blank">
        <img src="../assets/icons/mail.png" alt="Icon Mail"></a>
    </div>
    <div class="copyright">
      <p>&copy;2024 Maycon Henrique</p>
    </div>
    <img class="vector" src="../assets/Vector.png" alt="">
  </footer>
</template>

<style scoped>
footer {
  margin-top: 8rem;
  display: flex;
  flex-direction: column;
}

.icons {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 0.8rem;
}

.icons img {
  width: 2rem;
}

.copyright p {
  margin-top: 1rem;
  font-family: "Nunito", sans-serif;
  color: #828282;
  font-size: 0.8rem;
}

.vector{
  width: 100%;
  filter: grayscale(100%);
}
</style>
