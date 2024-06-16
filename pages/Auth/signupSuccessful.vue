<template>
    <div class="home">
        <h2>Hack Day</h2>

        <form submit.prevent="" class="mt-2">
            <h2>Check Your Email</h2>
            <p class="mt-1">Account creation successful, check your email for account activation</p>
            <button class="mt-1" type="button">
                <p>Sign in</p>
            </button>
        </form>
    </div>
</template>

<script setup>
import { onMounted } from 'vue';
import confetti from 'canvas-confetti';

onMounted(() => {
    const duration = 2 * 1000; // 2 seconds
    const end = Date.now() + duration;

    (function frame() {
        confetti({
            particleCount: 7,
            angle: 60,
            spread: 55,
            origin: { x: 0 }
        });
        confetti({
            particleCount: 7,
            angle: 120,
            spread: 55,
            origin: { x: 1 }
        });

        if (Date.now() < end) {
            requestAnimationFrame(frame);
        }
    })();
});
</script>

<style scoped>
.home {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;

    @media (width < 790px) {
        padding: 20px;
        justify-content: flex-start;
    }
}

.home form {
    padding: 40px;
    display: flex;
    flex-direction: column;
    border-radius: 8px;
    align-items: stretch;
    border: 1px solid #e5e4e4;
    width: 500px;

    @media (width < 790px) {
        border: none;
        padding: 15px;
        width: 100%;
    }
}

.home form h2 {
    font-size: 20px;
    text-align: center;
}

.home form p {
    text-align: center;
}

button {
    padding: 12px;
    border-radius: 4px;
    border: 0px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    background-color: black;
    color: #fff;
    font-weight: 600;
}

button p {
    color: #fff;
    font-weight: 600;
}
</style>
