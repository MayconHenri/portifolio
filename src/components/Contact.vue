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
      <div
        class="g-recaptcha"
        data-sitekey="6LerYIEqAAAAAAiYlfxDNfjEPS6qVW5Xem-bM-F6"
      ></div>
      <div class="buttons">
        <button @click="enviarEmail" class="submit">Enviar</button>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "@emailjs/browser"
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

      // Verificar se os campos estão preenchidos corretamente
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

      // Verificar se o reCAPTCHA foi preenchido
      const recaptchaResponse = grecaptcha.getResponse()
      if (!recaptchaResponse) {
        toast.error("Por favor, complete o reCAPTCHA.")
        valid = false
      }

      return valid
    },

    enviarEmail() {
      if (this.validarFormulario()) {
        const toast = useToast()

        // Obter a resposta do reCAPTCHA
        const recaptchaResponse = grecaptcha.getResponse()

        // Parâmetros do template que serão enviados para o EmailJS
        const templateParams = {
          from_name: this.name,
          from_email: this.email,
          message: this.message,
          recaptcha_response: recaptchaResponse
        }

        emailjs
          .send(
            "service_1qhqg1n",
            "template_z3e88ec",
            templateParams,
            "k-5AmYeSIWiFGDoaO"
          )
          .then(
            () => {
              toast.success("E-mail enviado com sucesso!")
              this.name = ""
              this.email = ""
              this.message = ""
            },
            (error) => {
              toast.error("Falha no envio. Tente novamente!")
              console.log("Falha no envio do e-mail:", error.text)
            }
          )
      }
    },
  },
  mounted() {
    const script = document.createElement("script")
    script.src = "https://www.google.com/recaptcha/api.js"
    document.head.appendChild(script)
  },
}
</script>

<style scoped>
/* Estilos básicos já existentes */

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

.g-recaptcha {
  margin-top: 1rem;
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


@media (max-width: 768px) {
  section {
    margin-top: 2rem;
  }

  .title h1 {
    font-size: 2.2rem;
  }

  .input-group {
    width: 90%; 
    max-width: 24rem; 
  }

  .input-group input,
  .input-group textarea {
    font-size: 0.9rem; 
  }

  .input-group .mensagem {
    height: 6rem; 
  }

  .g-recaptcha {
    width: 80%;
  }
}

@media (max-width: 480px) {
  .title h1 {
    font-size: 1.8rem;
  }

  .input-group input,
  .input-group textarea {
    font-size: 0.85rem;
  }

  .input-group .mensagem {
    height: 5rem;
  }
}

</style>
