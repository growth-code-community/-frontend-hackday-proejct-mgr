<template>
    <main class="center">
      <section>
        <h2 class="text-center mb-3">Hack Day</h2>
        <form class="p-2 center">
          <h3 class="mb-2">Check Your Email</h3>
          <p class="text-center mb-3">A link has been sent to your email, click on it to reset your password</p>
          <button class="mb-2">Sign In</button>
        </form>
      </section>
    </main>
  </template>
  
  <script></script>
  
  <style scoped>
  *{
      color: #1e1f1f;
  }
  main {
    background-color: #ffffff;
    height: 100vh;
  }
  label{
    margin-right: auto;
  }
  form {
    border: 1px solid #333;
    width: 40vw;
    border-radius: 10px   ;
    border: 1px solid #e5e4e4;
    @media(width<768px){
      width: 100vw;
      border: none;
    }
  }
  button{
      width: 100%;
      height: 3em;
      background-color: #1e1f1f;
      color: #ffffff;
      border-radius: 0.5px;
  }
  </style>
  