<template>
  <main class="forgot-password-page">
    <div class="container">
      <form @submit.prevent="handleSubmit" class="forgot-password-form">
        <h2>Forgot Your Password?</h2>
        <p>Please enter your email address to reset your password.</p>
        <input type="email" v-model="email" placeholder="Enter your email" required />
        <button type="submit">Send Reset Link</button>
      </form>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      email: '',
    };
  },
  methods: {
    handleSubmit() {
      // Handle the form submission
      alert(`Reset link sent to ${this.email}`);
    },
  },
};
</script>

<style>
.forgot-password-page {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #ffffff;
  font-family: 'Arial', sans-serif;
}

.container {
  background: white;
  padding: 40px 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 90%;
  width: 400px;
  margin: 0 auto;
}

.forgot-password-form {
  width: 100%;
  text-align: left;
}

.forgot-password-form h2 {
  margin-bottom: 20px;
  font-size: 24px;
  color: #333;
}

.forgot-password-form p {
  margin-bottom: 20px;
  font-size: 16px;
  color: #666;
}

.forgot-password-form input {
  width: 100%;
  padding: 15px 20px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 16px;
  box-sizing: border-box; /* Ensure padding and border are included in the element's total width and height */
}

.forgot-password-form button {
  width: 100%;
  padding: 15px 20px;
  border: none;
  border-radius: 5px;
  background-color: #000;
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.forgot-password-form button:hover {
  background-color: #141515;
}
</style>
