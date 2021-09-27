<template>
  <div class="form-background" id="form">
    <div class="container col-xl-10 col-xxl-8 px-4 py-5">
      <div class="row align-items-center g-lg-5 py-5">
        <div class="col-lg-7 text-center text-lg-start">
          <h1 class="display-4 fw-bold lh-1 mb-3">Оставить заявку</h1>
        </div>
        <div class="col-md-10 mx-auto col-lg-5">
          <form
            class="p-4 p-md-5 border rounded-3 bg-light"
            @submit.prevent="onSubmit"
          >
            <div class="form-floating mb-3">
              <input
                type="text"
                class="form-control"
                id="username"
                placeholder="Ваше имя"
                v-model.trim="username"
                :class="{ invalid: v$.username.$error }"
              />
              <label for="username">Ваше имя: </label>
              <small
                class="errValid"
                v-for="(error, idx) of v$.username.$errors"
                :key="idx"
              >
                {{ usernameValid(error.$validator) }}
              </small>
            </div>
            <div class="form-floating mb-3">
              <input
                type="tel"
                class="form-control"
                id="phone"
                placeholder="Телефон"
                v-model.trim="phone"
                :class="{ invalid: v$.phone.$error }"
              />
              <label for="phone">Телефон:</label>
              <small
                class="errValid"
                v-for="(error, idx) of v$.phone.$errors"
                :key="idx"
              >
                {{ phoneValid(error.$validator) }}
              </small>
            </div>
            <div class="form-floating mb-3">
              <input
                type="text"
                class="form-control"
                id="message"
                placeholder="Сообщение"
                v-model.trim="message"
                :class="{ invalid: v$.message.$error }"
              />
              <label for="message">Опишите задачу (кратко): </label>
              <small
                class="errValid"
                v-for="(error, idx) of v$.message.$errors"
                :key="idx"
              >
                {{ messageValid(error.$validator) }}
              </small>
            </div>
            <button
              class="w-100 btn btn-lg btn-warning"
              type="submit"
              @click="toast"
              :disabled="v$.$invalid"
            >
              Отправить
            </button>
            <hr class="my-4" />
            <small class="text-muted"
              >Нажимая кнопку "Отправить", вы соглашаетесь на обработку
              персональных данных!</small
            >
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import useVuelidate from "@vuelidate/core";
import { required, maxLength, minLength } from "@vuelidate/validators";
import { createToast } from "mosha-vue-toastify";
import "mosha-vue-toastify/dist/style.css";
import axios from "axios";

export default {
  name: "form",
  setup() {
    return {
      v$: useVuelidate(),
      toast: () => {
        createToast("Данные отправлены!");
      },
    };
  },
  data() {
    return {
      username: "",
      phone: "",
      message: "",
    };
  },

  validations: {
    username: { required, minLength: minLength(3), maxLength: maxLength(10) },
    phone: { required, minLength: minLength(6), maxLength: maxLength(16) },
    message: { required, minLength: minLength(10), maxLength: maxLength(100) },
  },

  methods: {
    onSubmit() {
      this.v$.$touch();
      if (this.v$.$error) {
        return;
      }

      const formData = {
        username: this.username,
        phone: this.phone,
        message: this.message,
      };

      console.log(formData);
      axios
        .post("http://127.0.0.1:5000", formData)
        .then((response) => {
          console.log(response);
        })
        .catch((e) => e.message);

      this.username = "";
      this.phone = "";
      this.message = "";
      setTimeout(() => {window.location.href = "/"}, 2000);
    },

    usernameValid($name) {
      if ($name === "required") {
        return "Поле не должно быть пустым";
      } else if ($name === "minLength") {
        return "Минимальная длинна должна быть 3 символов";
      } else if ($name === "maxLength") {
        return "Длинна не должна превышать 10 символов";
      }
    },
    phoneValid($name) {
      if ($name === "required") {
        return "Поле не должно быть пустым";
      } else if ($name === "minLength") {
        return "Минимальная длинна должна быть 6 символов";
      } else if ($name === "maxLength") {
        return "Длинна не должна превышать 14 символов";
      }
    },
    messageValid($name) {
      if ($name === "required") {
        return "Поле не должно быть пустым";
      } else if ($name === "minLength") {
        return "Минимальная длинна должна быть 10 символов";
      } else if ($name === "maxLength") {
        return "Длинна не должна превышать 100 символов";
      }
    },
  },
};
</script>


<style scoped>
.form-background {
  background-color: #f8f9fa;
}
.errValid {
  color: red;
}
</style>