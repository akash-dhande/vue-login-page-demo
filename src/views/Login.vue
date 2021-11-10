<template>
    <div class="auth-form-container">
        <h1>Welcome Back!</h1>
        <div class="page-info">Use these awesome forms to login or create new account in your project for free.</div>
        <form @submit.prevent="loginActionHandler" method="post" class="login-form">
            <h5>Sign in with credentials</h5>
            <div class="input-container email">
                <input v-model="email" type="email" placeholder="Email" />
            </div>
            <div class="input-container password">
                <input v-model="password" type="password" placeholder="Password" />
            </div>

            <div class="checkbox">
                <input type="checkbox" name="remember-me" id="remember-me" />
                <label for="remember-me">Remember me</label>
            </div>

            <div v-if="errors.length" class="errors">
                <ul>
                    <li v-for="(error, i) in errors" :key="i">{{ error }}</li>
                </ul>
            </div>
            <div class="buttons">
                <router-link v-if="false" class="button" to="/dashboard">Sign in</router-link>
                <button class="button" :class="{ loading: loading }" :disabled="loading" type="submit">Sign in</button>
            </div>

            <div class="form-links">
                <a href="#">Forgot password?</a>
                <a href="#">Create new account</a>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Login',
    data() {
        return {
            errors: [],
            email: null,
            password: null,
            loading: false,
        };
    },
    methods: {
        loginActionHandler() {
            this.errors = [];

            if (!this.email) {
                this.errors.push('Password is required.');
            }
            if (!this.password) {
                this.errors.push('Email is required.');
            }
            if (this.email && this.password) {
                this.loading = true;
                setTimeout(() => {
                    this.$router.push('dashboard');
                }, 1000);
            }
        },
    },
};
</script>
