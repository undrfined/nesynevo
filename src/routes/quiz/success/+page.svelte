<script lang="ts">
    import facebookIcon from "$lib/assets/facebook.svg";
    import googleIcon from "$lib/assets/google.svg";
    import emailIcon from "$lib/assets/mail.svg";
    import appleIcon from "$lib/assets/apple.svg";

    function login(){
        location.href = "/";
    }
</script>

<style>
    .page-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 20px;
        margin-top: 10dvh;
        color: #212121;
    }

    .header {
        text-align: center;
        margin-bottom: 20px;
    }

    .header h1 {
        font-size: 26px;
        margin-bottom: 10px;
    }

    .header p {
        font-size: 18px;
        color: #666;
    }

    .auth-button {
        background-color: #fff;
        border: 1px solid #ccc;
        border-radius: 8px;
        padding: 15px;
        margin: 10px 0;
        display: flex;
        align-items: center;
        font-size: 16px;
        width: 90%;
        max-width: 300px;
        color: black;
    }

    .auth-button:not(:has(img)) {
        justify-content: center;
    }

    .auth-button img {
        margin-right: 16px;
    }

    .terms {
        text-align: center;
        font-size: 12px;
        color: #888;
        margin-top: 30px;
    }
</style>

<div class="page-container">
    <div class="header">
        <h1>Happy you joined us!</h1>
        <p>Join the Fight Against Blood Shortages and Save Lives in Your Community</p>
    </div>
    <button class="auth-button" on:click={login}>
        <img src={emailIcon} alt="Email icon">Continue With Email
    </button>
    <button class="auth-button" on:click={login}>
        <img src={facebookIcon} alt="Facebook icon">Continue With Facebook
    </button>
    <button class="auth-button" on:click={login}>
        <img src={googleIcon} alt="Google icon">Continue With Google
    </button>
    <button class="auth-button" on:click={login}>
        <img src={appleIcon} alt="Apple icon">Continue With Apple
    </button>
    <button class="auth-button" on:click={login}>Sign In</button>
    <p class="terms">
        By signing in, you agree to our Terms of Service and acknowledge that you have read our Privacy Policy.
    </p>
</div>
