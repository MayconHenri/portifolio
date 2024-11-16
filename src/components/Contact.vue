<template>
  <section id="contatos">
    <div class="title">
      <h1>Contato</h1>
      <img src="@/assets/Rectangle19.png" alt="Tarja sobre o nome" />
    </div>
    <div class="container-form">
      <div class="input-group">
        <label for="Name">Nome</label>
        <input type="text" v-model="name" name="Name" id="Name" />
      </div>
      <div class="input-group">
        <label for="E-mail">E-mail</label>
        <input type="email" v-model="email" name="Email" id="Email" />
      </div>
      <div class="input-group">
        <label for="Mensagem">Mensagem</label>
        <textarea
          v-model="message"
          name="Mensagem"
          id="Mensagem"
          class="mensagem"
        ></textarea>
      </div>
      <div class="buttons">
        <button @click="enviarEmail" class="submit">Enviar</button>
      </div>
    </div>
  </section>
</template>

<script>
import { useToast } from "vue-toastification"

export default {
  name: "Contact",
  data() {
    return {
      name: "",
      email: "",
      message: "",
    }
  },
  methods: {
    validarFormulario() {
      let valid = true
      const toast = useToast()

      if (!this.name) {
        toast.error("Nome é obrigatório.")
        valid = false
      }

      if (!this.email) {
        toast.error("E-mail é obrigatório.")
        valid = false
      } else if (!/\S+@\S+\.\S+/.test(this.email)) {
        toast.error("Por favor, insira um e-mail válido.")
        valid = false
      }

      if (!this.message) {
        toast.error("Mensagem é obrigatória.")
        valid = false
      }

      return valid
    },

    enviarEmail() {
      if (this.validarFormulario()) {
        const toast = useToast()
        toast.success("E-mail enviado com sucesso!")
        this.name = ""
        this.email = ""
        this.message = ""

        // Implementar envio de e-mail
      }
    },
  },
}
</script>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 4rem;
}

.title {
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

.input-group {
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  width: 24rem;
}

.input-group label {
  font-family: "Nunito", sans-serif;
  font-size: 1rem;
  font-weight: 600;
  text-align: left;
}

.input-group input,
.input-group textarea {
  border: 1px solid #828282;
  padding: 0.4rem 0;
  padding-left: 0.8rem;
  border-radius: 8px;
  font-size: 1rem;
  font-family: "Nunito", sans-serif;
}

.input-group .mensagem {
  height: 8rem;
  padding: 0.8rem;
  resize: none;
}

.input-group input:focus,
.input-group textarea:focus {
  outline: none;
  border: 1px solid #424242;
  font-size: 1rem;
  font-family: "Nunito", sans-serif;
}

.buttons {
  display: flex;
  flex-direction: row;
  justify-content: right;
  margin-top: 1rem;
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
  transition: opacity 0.3s ease;
}

.buttons .submit {
  background-color: #828282;
  color: white;
}

.buttons .submit:hover {
  opacity: 0.6;
}
</style>
