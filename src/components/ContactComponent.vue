<template>
  <section id="contact" class="lower-section">
    <div>
      <h2>Contact</h2>
    </div>
    <div>
      <h4>Drop me a line</h4>
    </div>
    
    <div
      class="flex-grow justify-center px-8 lg:px-20"
    >
      <div class="flex justify-center">
        <div>
     
          <form
            id="contact-form"
            name="contact-form"
            method="post"
            data-netlify="true"
            autocomplete="off"
            netlify-honeypot="bot-field"
          >
            <input type="hidden" name="form-name" value="contact-form" />
            <div class="input-animated">
              <input
                type="text"
                id="contact-name"
                name="contact-name"
                required
                pattern="\S+.*"
                placeholder="the placeholder"
              />
              <label htmlFor="contact-name" class="label-name">
                <span class="content-name"> Name </span>
              </label>
            </div>
            <div class="input-animated">
              <input
                type="email"
                id="contact-email"
                name="contact-email"
                required
                placeholder="the placeholder"
              />
              <label htmlFor="contact-email" class="label-email">
                <span class="content-email"> Email </span>
              </label>
            </div>
            <div>
              <textarea
                name="contact-question"
                placeholder="Your Question"
                id="contact-question"
                cols="30"
                rows="5"
                minLength="10"
                maxLength="250"
                required
              ></textarea>
            </div>
            <button
              type="submit"
              id="submit-button"
              @click="handleSubmit"
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
                hover:bg-orange-300
                hover:text-black
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
import { ref } from "vue";

export default {
  name: "ContactComponent",
  components: {},
  setup() {
    
    let showError = ref(false);
    let showSuccess = ref(false);

    const handleErrors = (response) => {
      if (!response.ok) {
        throw Error(response.statusText);
      }
      return response;
    };

    const handleSubmit = async (e) => {
      e.preventDefault();
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
      handleSubmit
    };
  },
};
</script>