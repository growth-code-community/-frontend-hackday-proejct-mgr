<template>
  <main class="center">
    <section>
      <h2 class="text-center mb-3">Hack Day</h2>
      <form class="p-2 center">
        <h3 class="mb-3">Forgot Password?</h3>
        <label for="email" class="mb-1">Email</label>
        <input type="email" placeholder="lindaokolo@gmail.com" required class="mb-2"/>
        <button class="mb-2">Reset Password</button>
        <a href="#">Back to Sign In</a>
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
input{
    width: 100%;
    height: 3em;
    border: 1px solid #e1e2e7;
    border-radius: 0.5px;
}
button{
    width: 100%;
    height: 3em;
    background-color: #1e1f1f;
    color: #ffffff;
    border-radius: 0.5px;
}
a{
    text-decoration: none;
    font-weight: 600;
}
</style>
