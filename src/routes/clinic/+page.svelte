<script>
    // Script content for interactivity or data management
</script>

<style>
    /* CSS styles */
    .clinic-container {
        font-family: 'Arial', sans-serif;
        color: #333;
        max-width: 600px;
        margin: 0 auto;
        padding: 20px;
    }

    .clinic-header {
        background: #f0f0f0;
        border-radius: 10px;
        padding: 20px;
        margin-bottom: 20px;
        text-align: center;
    }

    .clinic-info {
        margin-bottom: 20px;
    }

    .section-title {
        font-size: 20px;
        margin-bottom: 10px;
    }

    .blood-checks {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
        margin-bottom: 20px;
    }

    .blood-check-item {
        background: #fff;
        border-radius: 10px;
        padding: 15px;
        text-align: center;
    }

    .reviews {
        margin-bottom: 20px;
    }

    .review-item {
        background: #fff;
        border-radius: 10px;
        padding: 15px;
        margin-bottom: 10px;
    }

    .donor-button {
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 20px;
        padding: 10px 20px;
        font-size: 16px;
        cursor: pointer;
        display: block;
        margin: 20px auto;
        text-align: center;
    }
</style>

<div class="clinic-container">
    <div class="clinic-header">
        <!-- Image placeholder -->
        <h1>VitalityCare Clinic</h1>
        <!-- Star rating placeholder -->
        <p>VitalityCare Clinic is a state-of-the-art medical facility dedicated to providing high-quality, compassionate care to patients of all ages Read More</p>
    </div>

    <div class="clinic-info">
        <p>🕒 Open now<br>8:00 AM - 10:00 PM</p>
        <p>📍 Address<br>1675 Broadway Broadway & 52nd Street, New York City, NY 10019–5820</p>
        <p>🏆 More than 148+ lives saved</p>
        <button class="donor-button" on:click={() => {
                location.href = "/clinic/appointment";

    }}>Became a blood donor</button>
    </div>

    <div class="section-title">Available blood checks</div>
    <div class="blood-checks">
        <div class="blood-check-item">Vitamin B12</div>
        <div class="blood-check-item">Vitamin D3</div>
        <div class="blood-check-item">Blood Type and Rh Factor</div>
    </div>

    <div class="section-title">Recent reviews</div>
    <div class="reviews">
        <div class="review-item">
            <p>Amanda Miers</p>
            <p>By donating blood, you are contributing to the health and well-being of others in need. It's a simple process that usually takes less than an hour and can potentially save multiple lives. Read More</p>
        </div>
        <!-- Additional reviews would go here -->
    </div>

    <button class="donor-button" on:click={() => {
                location.href = "/clinic/appointment";

    }}>Became a blood donor</button>
</div>
