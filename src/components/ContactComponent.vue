<template>
  <section id="contact" class="lower-section">
    <div>
      <h2>Contact</h2>
    </div>
    <div>
      <h4>I'd love to hear from you</h4>
    </div>

    <div class="flex-grow justify-center px-8 lg:px-20">
      <div class="flex justify-center">
        <div>
          <form
            id="contact-form"
            name="contact-form"
            method="post"
            data-netlify="true"
            autocomplete="off"
            netlify-honeypot="bot-field"
            @submit.prevent="handleSubmit"
          >
            <input type="hidden" name="form-name" value="contact-form" />
            <div class="input-animated">
              <input
                type="text"
                id="contact-name"
                name="contact-name"
                v-model="formState.name"
                required
                minLength="2"
                maxLength="50"
                pattern="\S+.*"
                placeholder="Name"
              />
              <label htmlFor="contact-name" class="label-name">
                <span class="content-name"> Name </span>
              </label>
            </div>
            <span v-if="v$.name.$error">
              {{ v$.name.$errors[0].$message }}
            </span>

            <div class="input-animated">
              <input
                type="email"
                id="contact-email"
                name="contact-email"
                v-model="formState.email"
                required
                placeholder="Email"
              />
              <label htmlFor="contact-email" class="label-email">
                <span class="content-email"> Email </span>
              </label>
            </div>
            <span v-if="v$.email.$error">
              {{ v$.email.$errors[0].$message }}
            </span>

            <div>
              <textarea
                name="contact-question"
                placeholder="Question"
                id="contact-question"
                cols="30"
                rows="5"
                minLength="10"
                maxLength="250"
                v-model="formState.question"
                required
              ></textarea>
            </div>
            <span v-if="v$.question.$error">
              {{ v$.question.$errors[0].$message }}
            </span>

            <button
              type="submit"
              id="submit-button"
              class="
                w-full
                font-semibold
                rounded-md
                uppercase
                text-center
                px-5
                py-3
                shadow-md
                my-4
                lg:mb-0
                transition-colors
                duration-500
                bg-orange-400
                text-white
                hover:bg-orange-300 hover:text-black
              "
            >
              Send Message
            </button>
            <div
              id="success"
              v-show="showSuccess"
              class="
                absolute
                mt-2
                px-4
                py-2
                font-medium
                border
                rounded-sm
                border-green-500
                bg-green-100
                text-green-600
              "
            >
              Thanks! We'll be in touch.
            </div>
            <div
              id="error"
              v-show="showError"
              class="
                absolute
                mt-2
                px-4
                py-2
                font-medium
                border
                rounded-sm
                border-red-500
                bg-red-100
                text-red-600
              "
            >
              Oops... Something went wrong.
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref, reactive, computed } from "vue";
import useValidate from "@vuelidate/core";
import { required, email, minLength, maxLength } from "@vuelidate/validators";

export default {
  name: "ContactComponent",
  components: {},
  setup() {

    let showError = ref(false);
    let showSuccess = ref(false);

    const formState = reactive({
      name: '',
      email: '',
      question: '',
    });

    const rules = computed(() => {
      return {
        name: { required, minLength: minLength(2), maxLength: maxLength(50) },
        email: { required, email },
        question: {
          required,
          minLength: minLength(10),
          maxLength: maxLength(250),
        },
      };
    });

    const v$ = useValidate(rules, formState);

    const handleErrors = (response) => {
      if (!response.ok) {
        throw Error(response.statusText);
      }
      return response;
    };

    const handleSubmit = async () => {
      const form = document.getElementById("contact-form");
      const formData = new FormData(form);

      fetch("/", {
        method: "POST",
        headers: { "Content-Type": "application/x-www-form-urlencoded" },
        body: new URLSearchParams(formData).toString(),
      })
        .then(handleErrors)
        .then(() => {
          showSuccess.value = true;
        })
        .catch((error) => {
          showError.value = true;
          console.log(error);
        });
    };

    return {
      showError,
      showSuccess,
      formState,
      v$,
      handleSubmit,
    };
  },
};
</script>