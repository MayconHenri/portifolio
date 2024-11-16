<script>
import menuIconOpen from '@/assets/images/icons/close_white_36dp.svg';
import menuIconClosed from '@/assets/images/icons/menu_white_36dp.svg';
export default {
  name: "Navbar",
  data() {
    return {
      isMenuOpen: false
    };
  },
  computed: {
    menuIcon() {
      return this.isMenuOpen ? menuIconOpen : menuIconClosed;
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
  }
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
    <div class="mobile-menu-icon">
      <button @click="toggleMenu">
        <img class="icon" :src="menuIcon" alt="">
      </button>
    </div>
    <ul class="mobile-menu" :class="{ open: isMenuOpen }">
      <li><a @click="closeMenu" href="#sobre">Sobre Mim</a></li>
      <li><a @click="closeMenu" href="#projetos">Projetos</a></li>
      <li><a @click="closeMenu" href="#contatos">Contatos</a></li>
    </ul>
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
  padding: 1.5rem 2rem;
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

.links a,
.title-name h1 {
  transition: opacity 0.3s ease;
  cursor: pointer;
}

.links a:hover,
.title-name h1:hover {
  opacity: 0.6;
}

.mobile-menu-icon {
  display: none;
}

.mobile-menu {
  display: none;
  position: absolute;
  top: 5rem;
  left: 0;
  width: 100%;
  background-color: #c6c6c6;
  z-index: 1000;
  text-align: center;
}

.mobile-menu li {
  padding-top: 1.2rem;
}
.mobile-menu li:first-child {
  padding-top: 0;
}
.mobile-menu.open {
  display: block;
}

@media (max-width: 600px) {
  .title-name {
    margin-left: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  nav {
    display: flex;
    margin: 0;
    padding: 1.5rem 2rem;
    justify-content: space-between;
  }

  .links {
    display: none;
  }

  .mobile-menu-icon {
    display: block;
  }

  .mobile-menu-icon button {
    background-color: transparent;
    border: none;
    cursor: pointer;
  }

  .mobile-menu {
    display: none;
    flex-direction: column;
    padding-bottom: 1rem;
    margin-top: 1.5rem;
    list-style: none;

  }

  .mobile-menu li {
    display: flex;
    flex-direction: column;
    gap: 12rem;
  }

  .mobile-menu.open {
    display: block;
  }
}

@media (min-width: 600px) and (max-width: 1024px) {
  nav {
    padding: 1.5rem 1rem;
  }
}

</style>
