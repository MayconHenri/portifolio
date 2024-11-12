<script>
export default {
  name: "Footer",
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
  },
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
    <button @click="scrollToTop" class="scroll-to-top">
      ↑
  </button>
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
  transition: opacity 0.3s ease;
}

.icons img:hover {
  opacity: 0.6;
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
  height: 14rem;
}
.scroll-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background-color: #828282;
  color: white;
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  font-size: 1.5rem;
  cursor: pointer;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  transition: opacity 0.3s ease;
}

.scroll-to-top:hover {
  opacity: 0.8;
}

</style>
