<script>
    // Include any necessary script logic for buttons
    function addToCalendar() {
        // Logic to add to calendar
    }

    function sendReminder() {
        // Logic to send a reminder
    }
</script>

<style>
    .page-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 20px;
        height: 100vh;
        box-sizing: border-box;
        font-family: 'Arial', sans-serif;
        background: white;
    }

    .message {
        text-align: center;
        margin-bottom: 50px;
    }

    .message h1 {
        margin: 0;
        font-size: 24px;
        color: #333;
    }

    .message p {
        color: #666;
        font-size: 16px;
    }

    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 15px 30px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 10px;
        background: white;
        color: #333;
        font-size: 16px;
        cursor: pointer;
    }

    /* Placeholder for the icons next to the button text */
    .icon {
        margin-right: 10px;
        display: inline-block;
        width: 20px;
        height: 20px;
        background: #ccc;
        mask: url('/path-to-icon.svg') no-repeat 50% 50%;
        mask-size: contain;
    }
</style>

<div class="page-container">
    <div class="message">
        <h1>Thank You!</h1>
        <p>Thank you for being a part of our community. You will be notified within 24 hours of receiving the results of your blood check</p>
    </div>
    <button class="button" on:click={addToCalendar}>
        <span class="icon"></span> Add To Calendar
    </button>
    <button class="button" on:click={sendReminder}>
        <span class="icon"></span> Send Me Reminder
    </button>
</div>
