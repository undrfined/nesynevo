<script lang="ts">
    import facebookIconFilled from '$lib/assets/facebook-fill.svg';
    import twitterIconFilled from '$lib/assets/twitter-fill.svg';
    import instagramIconFilled from '$lib/assets/instagram-fill.svg';
    import shareIconFilled from '$lib/assets/share-fill.svg';
</script>

<style>
    .container {
        width: 100%;
        max-width: 570px;
        margin-top: 30dvh;

        text-align: center;
        padding: 20px;
    }

    .title {
        color: #333;
        font-size: 24px;
        margin-bottom: 20px;
    }

    .message {
        font-size: 18px;
        color: #666;
        margin-bottom: 30px;
    }

    .code {
        background-color: #f5f5f5;
        padding: 10px;
        border-radius: 5px;
        font-size: 18px;
        margin-bottom: 20px;
    }

    .social-buttons {
        display: flex;
        justify-content: center;
        gap: 10px;
        margin-bottom: 20px;
    }

    .social-button {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 50px;
        height: 50px;
        border-radius: 25px;
        border: 1px solid #ddd;
    }

    /* You should add actual icons here using an icon library or SVGs */
    .icon {
        width: 20px;
        height: 20px;
    }
</style>

<div class="container">
    <h1 class="title">You can still help us!</h1>
    <p class="message">
        We regret to inform you that you are ineligible to donate blood. However, you can still support us by sharing an invitation link and helping us reach more potential donors.
    </p>
    <div class="code">FRIEND9YXVN</div>
    <div class="social-buttons">
        <div class="social-button"><img src={facebookIconFilled} class="icon"></div>
        <div class="social-button"><img src={twitterIconFilled}  class="icon"></div>
        <div class="social-button"><img  src={instagramIconFilled} class="icon"></div>
        <div class="social-button"><img  src={shareIconFilled} class="icon"></div>
    </div>
</div>
