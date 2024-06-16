<template>
    <div class="home">
        <h2>Hack Day</h2>

        <form submit.prevent="" class="mt-2">
            <div class="container mt-1">
                <!-- Password -->
                <label class="mt-2 weight-5" for="password">Reset password</label>
                <div class="password mt-1">
                    <input v-if="showPassword" type="text" name="" id="password" v-model="password"
                        placeholder="********">
                    <input v-else type="password" name="" id="password" v-model="password" placeholder="********">
                    <div @click="toggleShowPassword" class="visbilty">
                        <img v-if="showPassword" src="@/assets/icons/visibility_off.svg" alt="">
                        <img v-else src="@/assets/icons/visibility.svg" alt="">
                    </div>
                </div>

                <!-- Password Requirements -->
                <span class="passwordRequirement">
                    <img v-show="isLengthValid" src="@/assets/icons/check_mark.svg" alt="" draggable="false">
                    <p :class="{ valid: isLengthValid }">At least 8 characters</p>
                </span>
                <span class="passwordRequirement">
                    <img v-show="hasSpecialCharacter" src="@/assets/icons/check_mark.svg" alt="" draggable="false">
                    <p :class="{ valid: hasSpecialCharacter }">At least a special character</p>
                </span>
                <span class="passwordRequirement">
                    <img v-show="hasNumber" src="@/assets/icons/check_mark.svg" alt="" draggable="false">
                    <p :class="{ valid: hasNumber }">At least 1 numerical character</p>
                </span>
                <span class="passwordRequirement">
                    <img v-show="hasUpperCase" src="@/assets/icons/check_mark.svg" alt="" draggable="false">
                    <p :class="{ valid: hasUpperCase }">At least 1 upper case character</p>
                </span>

                <!-- confirmPassword -->
                <label class="mt-2 weight-5" for="confirmPassword">Confirm Password</label>
                <div class="password mt-1">
                    <input v-if="showConfirmPassword" type="text" name="" id="confirmPassword" v-model="confirmPassword"
                        placeholder="********">
                    <input v-else type="password" name="" id="confirmPassword" v-model="confirmPassword"
                        placeholder="********">
                    <div @click="toggleShowConfirmPassword" class="visbilty">
                        <img v-if="showConfirmPassword" src="@/assets/icons/visibility_off.svg" alt="">
                        <img v-else src="@/assets/icons/visibility.svg" alt="">
                    </div>
                </div>

                <span v-show="password && confirmPassword" class="passwordRequirement mt-1">
                    <img v-show="passwordsMatch" src="@/assets/icons/check_mark.svg" alt="" draggable="false">
                    <p v-if="passwordsMatch" :class="{ valid: passwordsMatch }">Passwords Match</p>
                    <p v-else :class="{ invalid: !passwordsMatch }">Passwords do not match</p>
                </span>

                <button class="mt-1" type="button" @click="resetPassword">Reset Password</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            showPassword: false,
            password: '',
            showConfirmPassword: false,
            confirmPassword: '',
        }
    },
    computed: {
        isLengthValid() {
            return this.password.length >= 8;
        },
        hasSpecialCharacter() {
            return /[!@#$%^&*(),.?":{}|<>]/.test(this.password);
        },
        hasNumber() {
            return /\d/.test(this.password);
        },
        hasUpperCase() {
            return /[A-Z]/.test(this.password);
        },
        passwordsMatch() {
            return this.password === this.confirmPassword && this.confirmPassword !== '';
        }
    },
    methods: {
        toggleShowPassword() {
            this.showPassword = !this.showPassword;
        },
        toggleShowConfirmPassword() {
            this.showConfirmPassword = !this.showConfirmPassword;
        },
        resetPassword() {
            if (this.isLengthValid && this.hasSpecialCharacter && this.hasNumber && this.hasUpperCase && this.passwordsMatch) {
                // Perform password reset logic here
                alert("Password reset successfully!");
            } else {
                alert("Please meet all password requirements and ensure passwords match.");
            }
        }
    }
}
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
        justify-content: flex-start
    }
}

.home form {
    padding: 40px;
    display: flex;
    flex-direction: column;
    border-radius: 8px;
    border: 1px solid #e5e4e4;

    @media (width < 790px) {
        border: none;
        padding: 15px;
        width: 100%;
    }
}

.home form .container {
    display: flex;
    flex-direction: column;
}

.home form .container .content {
    display: flex;
    align-items: center;
    flex-direction: column;
}

.home form .container .content label {
    color: #1E1E1ECC;
}

.home form .container .password {
    width: 415px;
    padding: 12px;
    border: 1px solid #6B728033;
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: space-between;

    @media (width < 790px) {
        width: 100%;
    }
}


.home form .container .password input {
    padding: 0px;
    border: 0px;
    outline: none;
    width: 100%;
    height: 20px;
}

.home form .container .password .visbilty {
    border: none;
    outline: 0px;
    background: transparent;
    width: 20px;
    height: 20px;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.passwordRequirement {
    display: flex;
    gap: 10px;
    align-items: center;
}


.passwordRequirement p {
    font-size: 14px !important;
    margin: 0;
}

.passwordRequirement p.valid {
    color: green;
    font-weight: bold;
}

.passwordRequirement p.invalid {
    color: red;
    font-weight: bold;
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
</style>
