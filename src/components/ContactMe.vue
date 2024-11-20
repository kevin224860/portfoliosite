<template>
  <section id="ContactMe" class="contact-container">
    <h1>Contact Me</h1>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <input type="text" id="name" v-model="form.name" placeholder="Your Name" required />
      </div>
      <div class="form-group">
        <input type="email" id="email" v-model="form.email" placeholder="Your Email" required />
      </div>
      <div class="form-group">
        <textarea id="message" v-model="form.message" placeholder="Your Message" rows="5" required></textarea>
      </div>
      <button type="submit">Send Message</button>
    </form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    };
  },
  methods: {
    handleSubmit() {
      alert('Thank you for contacting me! I will get back to you soon.');
      this.form.name = '';
      this.form.email = '';
      this.form.message = '';
    }
  }
};
</script>

<style scoped>
.contact-container {
  max-width: 600px;
  margin: 250px auto;
  padding: 20px;
  background-color: #252539;
  border-radius: 12px;
  color: #fff;
  box-shadow: 0 4px 5px #64f1b2;
  scroll-margin-top: 150px; /* Ensures the component is not flush with the top */

}

h1 {
  font-size: 30px;
  margin-bottom: 20px;
  text-align: center;
  color: var(--primary-color);
}

form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.form-group {
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 5px;
  color: #ddd;
}

input, textarea {
  padding: 10px;
  border: none;
  border-radius: 8px;
  background-color: #333;
  color: #fff;
  font-size: 16px;
  outline: none;
}

input:focus, textarea:focus {
  border: 2px solid var(--primary-color);
}

button {
  padding: 12px;
  background: linear-gradient(to right, var(--primary-color), #64f1b2);
  color: #fff;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  transition: background 0.3s, transform 0.2s, box-shadow 0.2s;
}

button:hover {
  background: linear-gradient(to right, #64f1b2, var(--primary-color));
  box-shadow: 0 5px 20px rgba(100, 241, 178, 0.3);
  transform: scale(1.05); /* Slight zoom-in effect */
}

@media (max-width: 600px) {
  h1 {
    font-size: 24px;
  }
  input, textarea {
    font-size: 14px;
  }
  button {
    font-size: 14px;
    padding: 10px;
  }
}
</style>
